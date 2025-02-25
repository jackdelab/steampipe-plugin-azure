# Table: azure_compute_disk_metric_read_ops

Azure Monitor metrics provide data about the performance of your systems. The `azure_compute_disk_metric_read_ops` table provides metric statistics at 5 minutes intervals for the most recent 5 days.

## Examples

### Basic info

```sql
select
  name,
  timestamp,
  minimum,
  maximum,
  average,
  sample_count
from
  azure_compute_disk_metric_read_ops
order by
  name,
  timestamp;
```

### Operations Over 10 Bytes average

```sql
select
  name,
  timestamp,
  round(minimum::numeric,2) as min_read_ops,
  round(maximum::numeric,2) as max_read_ops,
  round(average::numeric,2) as avg_read_ops,
  sample_count
from
  azure_compute_disk_metric_read_ops
where
  average > 10
order by
  name,
  timestamp;
```
