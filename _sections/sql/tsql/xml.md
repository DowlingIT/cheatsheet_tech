---
title: XML
subtopic: tsql
group: JSON & XML
order: 2
---

#### Native XML column

```sql
CREATE TABLE docs (id INT PRIMARY KEY, payload XML);

SELECT payload.value('(/root/name)[1]', 'NVARCHAR(100)') FROM docs;   -- extract a value
SELECT payload.query('/root/items') FROM docs;                          -- extract a node set
UPDATE docs SET payload.modify('replace value of (/root/name/text())[1] with "New"');
```

#### Rows → XML

```sql
SELECT id, name FROM users FOR XML PATH('user'), ROOT('users');
SELECT id, name FROM users FOR XML AUTO, ELEMENTS;
```
