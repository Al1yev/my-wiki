## PIVOT Operator in SQL

### What is **PIVOT**

**PIVOT** - bu SQL Operatori bo'lib, qatorlarni ustunlarga o'zgartirish yoki aksincha, ustunlarni qatorlarga o'zgartirish imkonini beruvchi operator hisoblanadi. Pivot operatsiyasi, ayniqsa, ma'lumotlarni jadvaldagi satrlardan ustunlarga o'zgartirmoqchi bo'lganingizda foydali bo'lib, ularni tahlil qilish yoki boshqa formatda taqdim etishni osonlashtiradi.

<hr>

### Syntax

```
SELECT *
FROM (
    SELECT [pivot_column], [value_column]
    FROM [your_table]
) AS SourceTable
PIVOT (
    AGGREGATE_FUNCTION([value_column])
    FOR [pivot_column] IN ([value1], [value2], [value3], ...,[valueN])
) AS PivotTable;
```

- SourceTable - bu ustunlarini pivot qilmoqchi bo'lgan subquery;
- PIVOT kalit so'zidan keyin "value_column"idagi qiymatlarga qo'llaniladigan agregat funksiya (masalan, SUM, AVG, COUNT va boshqalar) keladi;
- FOR bandi "pivot_column" dagi siz natijada ustun bo'lishni xohlagan qiymatlarni belgilaydi;
- Natijada "pivot_column"dagi belgilangan qiymatlar ustunlarga aylanadi va yig'ish funksiyasi "value_column" dagi mos qiymatlarga qo'llaniladigan jadvaldir.

<hr>

### Why should we use **PIVOT**

**PIVOT** kalit so'zi odatda ma'lumotlarni o'zgartirish paytida umumlashtirish uchun umumiy funktsiyalar bilan birgalikda ishlatiladi.

<hr>

### When should we use **PIVOT**

SQL-da **PIVOT**dan foydalanish bir necha sabablarga ko'ra juda foydali bo'lishi mumkin, ayniqsa ma'lumotlarni tahlil qilish, hisobot berish va taqdimot bilan shug'ullanganda.

<hr>

### Example for **PIVOT**

### Note

> MySQL-da SQL Server kabi o'rnatilgan PIVOT funksiyasi yo'q. Shu bilan birga, condition aggregation va case statements kombinatsiyasidan foydalanib, pivotga o'xshash effektga erishishingiz mumkin. Usul siz aylantirmoqchi bo'lgan har bir toifa uchun virtual ustun yaratishni va ushbu ustunlarni to'ldirish uchun jamlash funktsiyalaridan foydalanishni o'z ichiga oladi.

```
SELECT
    Date,
    SUM(CASE WHEN Product = 'Product A' THEN Amount ELSE 0 END) AS 'Product A',
    SUM(CASE WHEN Product = 'Product B' THEN Amount ELSE 0 END) AS 'Product B'
FROM
    Sales
GROUP BY
    Date;

```

- [Main Page](https://github.com/Al1yev/my-wiki/tree/main)
