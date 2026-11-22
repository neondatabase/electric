---
'@core/sync-service': patch
---

Fix composite subqueries whose columns are not in alphabetical order, such as `(viewer_id, owner_id) IN (SELECT viewer_id, owner_id FROM grants)`: their columns were sorted and compared at the wrong positions, so the shape returned nothing, or the rows of the swapped relation.
