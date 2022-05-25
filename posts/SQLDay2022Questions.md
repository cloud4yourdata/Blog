# SQL Day 2022 - Zagadki SQL

## Challange 1
Jaki jest wynik poniższego zapytania:
```sql
DECLARE @t TABLE( Val INT);
DROP TABLE IF EXISTS #temp;
CREATE TABLE #temp (Val INT);

BEGIN TRAN;
	INSERT INTO @t(Val) SELECT 1;
	INSERT INTO #temp(Val) SELECT 2;
ROLLBACK TRAN;

SELECT * FROM @t
UNION ALL
SELECT * FROM #temp;
DROP TABLE IF EXISTS #temp;
```
**Wyjaśnienie:**