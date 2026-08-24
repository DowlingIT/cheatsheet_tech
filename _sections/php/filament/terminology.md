---
title: Concepts & Terms
subtopic: filament
group: Overview
order: 1
---

#### Panel & structure

```
Panel            The admin area — owns a URL path, auth, navigation, and all its resources
Resource         Full CRUD interface auto-generated for a model (list, create, edit pages)
Page             Custom full-page view registered in a panel — not tied to a model
Widget           Dashboard tile — Stats, Chart, or Table widget; placeable on pages
Relation Manager Inline CRUD for a model's relationship on the edit page (Post → Comments)
Infolist         Read-only record display using Entry components (vs Form for editing)
Plugin           Installable package that extends a panel with resources, widgets, pages
```

#### Forms & tables

```
Form         Filament's form builder — a schema of Field components
Field        A form input (TextInput, Select, Toggle, FileUpload, Repeater, …)
Table        Filament's table builder — a schema of Columns + Filters + Actions
Column       A table cell renderer (TextColumn, ImageColumn, BadgeColumn, …)
Filter       Reduces table rows — SelectFilter, TernaryFilter, custom Filter
Action       Button with side effects — can open a modal, confirm, or run code inline
Bulk Action  Action applied to all selected table rows at once
```

#### Field & column modifiers

```
->live()        re-renders the form when this field changes (for reactive fields)
->searchable()  adds search box to a Select or enables global search on a Column
->sortable()    makes a table column header clickable for sorting
->toggleable()  lets users show/hide a column via the column picker
->badge()       renders a TextColumn as a coloured badge pill
```
