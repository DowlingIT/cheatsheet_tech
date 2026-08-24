---
title: Field Types
subtopic: django
group: Models
order: 3
---

#### String & numbers

```python
models.CharField(max_length=200)
models.TextField()                 models.EmailField()
models.URLField()                  models.SlugField(unique=True)
models.UUIDField(default=uuid.uuid4, editable=False)

models.IntegerField()              models.BigIntegerField()
models.PositiveIntegerField()      models.SmallIntegerField()
models.FloatField()
models.DecimalField(max_digits=10, decimal_places=2)
```

#### Date, bool & other

```python
models.BooleanField(default=False)
models.DateField(auto_now_add=True)
models.DateTimeField(auto_now=True)      # updated on every save
models.TimeField()                        models.DurationField()
models.JSONField(default=dict)
models.FileField(upload_to='uploads/%Y/%m/')
models.ImageField(upload_to='images/')   # needs Pillow
```

#### Common field options

```python
null=True           # allow NULL in DB (use blank=True for forms)
blank=True          # allow empty in form validation
default=0           # or callable: default=list
unique=True         db_index=True
choices=[('d','Draft'),('p','Published')]
verbose_name='published at'
editable=False      # hide from forms/admin
```
