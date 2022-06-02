# Spark Settings

```python
df = spark.sql("SET -v")
df.createOrReplaceTempView("SparkSettings")
```

```sql
SELECT * FROM SparkSettings WHERE key ILIKE '%%' 
```
