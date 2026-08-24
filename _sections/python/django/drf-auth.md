---
title: DRF Auth & Permissions
subtopic: django
group: DRF
order: 4
---

#### Authentication classes

```python
from rest_framework.authentication import (
    SessionAuthentication,      # browser / cookie-based
    BasicAuthentication,        # HTTP Basic (dev only)
    TokenAuthentication,        # DRF built-in token (Authorization: Token abc123)
)
# Third-party
from rest_framework_simplejwt.authentication import JWTAuthentication
```

#### Permission classes

```python
from rest_framework.permissions import (
    AllowAny,
    IsAuthenticated,
    IsAdminUser,
    IsAuthenticatedOrReadOnly,   # GET open, write needs auth
)

# Custom permission
class IsOwnerOrReadOnly(BasePermission):
    def has_object_permission(self, request, view, obj):
        if request.method in SAFE_METHODS:
            return True
        return obj.author == request.user
```

#### Per-view override

```python
from rest_framework.decorators import api_view, permission_classes, authentication_classes

@api_view(['GET', 'POST'])
@permission_classes([IsAuthenticated])
def my_view(request): ...

class PostViewSet(viewsets.ModelViewSet):
    permission_classes = [IsOwnerOrReadOnly]
    authentication_classes = [JWTAuthentication]
```
