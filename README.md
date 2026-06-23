# Projekt końcowy – Relacyjne bazy danych

## Temat projektu

System zarządzania danymi bioinformatycznymi.

## Wyniki zapytań SQL

### Zapytanie 4ii

```sql
SELECT
    t.test_type,
    COUNT(DISTINCT pt.patient_id) AS liczba_pacjentow
FROM tests t
JOIN patient_test pt ON t.test_id = pt.test_id
GROUP BY t.test_type
HAVING COUNT(DISTINCT pt.patient_id) > 30;
```

**Wynik**

| test_type | liczba_pacjentow |
|------------|------------------|
| NGS-panel | 38 |
| SNP Array | 39 |

### Zapytanie 4iii

```sql
SELECT
    t.test_type,
    AVG(warianty.liczba_wariantow) AS srednia_liczba_wariantow
FROM (
    SELECT test_id, COUNT(*) AS liczba_wariantow
    FROM results
    GROUP BY test_id
) warianty
JOIN tests t ON warianty.test_id = t.test_id
GROUP BY t.test_type;
```

**Wynik**

| test_type | srednia_liczba_wariantow |
|------------|--------------------------|
| SNP Array | 3.0000 |
| NGS-panel | 3.6857 |
| WES | 3.5294 |
| WGS | 3.6071 |

## Pliki CSV

- patients_tests.csv
- patients_both_tests.csv
- pathogenic_results.csv
