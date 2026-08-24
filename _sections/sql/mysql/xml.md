---
title: XML
subtopic: mysql
group: JSON & XML
order: 2
---

#### Limited, deprecated support

```sql
SELECT ExtractValue(payload, '/root/name') FROM docs;                     -- deprecated 8.0+
SELECT UpdateXML(payload, '/root/name', '<name>New</name>') FROM docs;      -- deprecated 8.0+
```

MySQL has no dedicated XML type and only these two limited, deprecated functions. Prefer JSON — it's a fully first-class type with real indexing and function support.
