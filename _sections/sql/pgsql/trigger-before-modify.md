---
title: Modifying Rows in BEFORE Triggers
subtopic: pgsql
group: Triggers
order: 3
---

#### BEFORE can change or cancel the write; AFTER can't

```sql
CREATE FUNCTION set_updated_at() RETURNS TRIGGER AS $$
BEGIN
  NEW.updated_at := NOW();     -- BEFORE triggers can modify NEW before it's written
  RETURN NEW;                    -- returning NULL cancels the operation entirely
END;
$$ LANGUAGE plpgsql;

CREATE TRIGGER trg_set_updated_at
BEFORE UPDATE ON users
FOR EACH ROW EXECUTE FUNCTION set_updated_at();
```

In `AFTER` triggers, `NEW`/`OLD` are read-only and the function's return value is ignored — the write already happened.
