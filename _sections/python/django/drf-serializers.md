---
title: DRF Serializers
subtopic: django
group: DRF
order: 1
---

#### ModelSerializer

```python
from rest_framework import serializers
from .models import Post

class PostSerializer(serializers.ModelSerializer):
    author_name = serializers.SerializerMethodField()
    tag_names   = serializers.StringRelatedField(
        source='tags', many=True, read_only=True)

    class Meta:
        model  = Post
        fields = ['id', 'title', 'slug', 'body', 'status',
                  'author', 'author_name', 'tag_names', 'created_at']
        read_only_fields = ['slug', 'created_at']

    def get_author_name(self, obj):
        return obj.author.get_full_name()
```

#### Validation & create/update

```python
class PostSerializer(serializers.ModelSerializer):
    def validate_title(self, value):
        if len(value) < 5:
            raise serializers.ValidationError('Title too short')
        return value

    def validate(self, data):
        if data['status'] == 'published' and not data.get('slug'):
            raise serializers.ValidationError('Published posts need a slug')
        return data

    def create(self, validated_data):
        tags = validated_data.pop('tags', [])
        post = Post.objects.create(**validated_data)
        post.tags.set(tags)
        return post

    def update(self, instance, validated_data):
        tags = validated_data.pop('tags', None)
        for attr, value in validated_data.items():
            setattr(instance, attr, value)
        instance.save()
        if tags is not None:
            instance.tags.set(tags)
        return instance
```
