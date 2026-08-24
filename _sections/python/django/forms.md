---
title: Forms
subtopic: django
group: Views & Forms
order: 1
---

#### forms.Form

```python
from django import forms

class ContactForm(forms.Form):
    name    = forms.CharField(max_length=100)
    email   = forms.EmailField()
    message = forms.CharField(widget=forms.Textarea)

    def clean_email(self):
        email = self.cleaned_data['email']
        if 'spam' in email:
            raise forms.ValidationError('Invalid email address')
        return email

    def clean(self):
        cleaned = super().clean()
        # cross-field validation here
        return cleaned
```

#### ModelForm

```python
class PostForm(forms.ModelForm):
    class Meta:
        model   = Post
        fields  = ['title', 'slug', 'body', 'status']
        # or: exclude = ['author', 'created_at']
        widgets = {'body': forms.Textarea(attrs={'rows': 10})}

    def save(self, commit=True):
        instance = super().save(commit=False)
        # inject or override fields before saving
        if commit:
            instance.save()
            self.save_m2m()
        return instance
```
