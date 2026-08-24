---
title: XML
subtopic: pgsql
group: JSON & XML
order: 2
---

#### Native XML column

```sql
CREATE TABLE docs (id SERIAL PRIMARY KEY, payload XML);

SELECT xpath('/root/name/text()', payload) FROM docs;         -- returns an array of matches
SELECT xpath_exists('/root/name', payload) FROM docs;
```

#### Building XML

```sql
SELECT xmlelement(name "user", xmlattributes(id AS "id"), name) FROM users;
```

Postgres XML support is read/build-oriented — there's no in-place `.modify()` like T-SQL; reconstruct the value instead.
