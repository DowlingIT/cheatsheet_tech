---
title: DRF Views & ViewSets
subtopic: django
group: DRF
order: 2
---

#### APIView

```python
from rest_framework.views import APIView
from rest_framework.response import Response
from rest_framework import status

class PostListView(APIView):
    def get(self, request):
        posts = Post.objects.filter(status='published')
        serializer = PostSerializer(posts, many=True)
        return Response(serializer.data)

    def post(self, request):
        serializer = PostSerializer(data=request.data)
        if serializer.is_valid():
            serializer.save(author=request.user)
            return Response(serializer.data, status=status.HTTP_201_CREATED)
        return Response(serializer.errors, status=status.HTTP_400_BAD_REQUEST)
```

#### ModelViewSet

```python
from rest_framework import viewsets
from rest_framework.decorators import action

class PostViewSet(viewsets.ModelViewSet):
    queryset           = Post.objects.all()
    serializer_class   = PostSerializer
    permission_classes = [IsAuthenticatedOrReadOnly]

    def get_queryset(self):
        qs = super().get_queryset()
        if status := self.request.query_params.get('status'):
            qs = qs.filter(status=status)
        return qs

    def perform_create(self, serializer):
        serializer.save(author=self.request.user)

    @action(detail=True, methods=['post'])
    def publish(self, request, pk=None):
        post = self.get_object()
        post.status = 'published'
        post.save()
        return Response({'status': 'published'})
```
