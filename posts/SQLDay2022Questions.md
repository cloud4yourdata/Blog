# SQL Day 2022 - Zagadki SQL

## Zadanie 1
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
### Wyjaśnienie:
Tutaj istotne jest zrozumienie różnic pomiędzy tabelami tymczasowymi i zmiennymi tabelarycznymi.
Jedną z istotnych różnic jest fakt, że transakcje "nie obowiązują" dla zmiennych tabelarycznych.
Zatem wycofanie transakcji nie spowoduje "wycofania" danych wstawionych do zmiennej tabelarycznej @t.
Wynikiem zapytanie będzie result set z jednym rekordem.
