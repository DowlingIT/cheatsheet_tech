---
title: File Structure
subtopic: filament
group: Overview
order: 3
---

#### Layout

```
app/
  Filament/
    Resources/
      PostResource.php              main resource class (form + table defined here)
      PostResource/
        Pages/
          ListPosts.php             index page
          CreatePost.php            create page
          EditPost.php              edit page
          ViewPost.php              read-only view page (optional)
        RelationManagers/
          CommentsRelationManager.php

    Pages/
      Settings.php                  custom panel page

    Widgets/
      StatsOverview.php             dashboard widget

  Providers/
    Filament/
      AdminPanelProvider.php        panel config — path, auth, colors, plugins

resources/views/
  filament/                         blade overrides (optional)
    resources/
      posts/
        pages/
          edit-post.blade.php       override a generated page's blade
```

#### Key conventions

```
PostResource.php        → posts table, Post model, /admin/posts URL
--generate flag         auto-fills form + table schema from model $fillable / casts
getPages()              registers URL routes for the resource's pages
getRelations()          registers RelationManagers shown on the edit page
getWidgets()            registers widgets shown in the resource's header/footer
```
