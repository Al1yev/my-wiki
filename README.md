## VIEW in SQL

- ### What is **VIEW**

  SQLda **VIEW** virtual jadval bo'lib, u SELECT so'rovi natijasiga asoslanadi. **VIEW** ma'lumotlarni o'zi saqlamaydi, lekin so'rov natijalari to'plamini xuddi jadval kabi ko'rsatish usulini beradi.

<hr>

- ### Syntax

  ```SQL
  CREATE VIEW view_name AS
  SELECT column1, column2.....
  FROM table_name
  WHERE condition;
  ```

  **view_name**: Name for the View
  **column1, column2...**: Columns you want to include in your view
  **table_name**: Name of the table
  **condition**: Condition to select rows

<hr>

- ### Why should we use **VIEW**

  **VIEW** murakkab so'rovlarni soddalashtirish, ma'lum ustunlar yoki qatorlarga kirishni cheklash orqali xavfsizlik darajasini ta'minlash va murakkab mantiqni qamrab olish uchun ishlatilishi mumkin.

<hr>

- ### When should we use **VIEW**

  **Murakkab querylarni soddalashtirish**: Agar siz tez-tez murakkab querylarni ishlatsangiz, VIEW bu murakkablikni sodda ko'rinishga olib kelishi mumkin;

  **Xavfsizlik**: VIEW ma'lumotlarning ma'lum qatorlari yoki ustunlariga foydalanuvchi kirishini cheklashi mumkin

  **Qayta foydalaniluvchan kod**: Agar siz o'zingizni ilovangiz yoki ma'lumotlar bazasining turli qismlarida bir xil yoki o'xshash query larni qayta-qayta yozayotgan bo'lsangiz, VIEW bu mantiqni qamrab oladi, bu esa kodingizni toza va qayta foydalanishga imkon beradi.

  **Mantiqiy ma'lumotlarni ko'rsatish**: VIEW biznes mantig'i yoki foydalanuvchi talablariga ko'proq mos keladigan ma'lumotlarning boshqa ko'rinishini taqdim etishi mumkin. Misol uchun, siz keng qamrovli mijoz profilini taqdim qilish uchun bir nechta jadvallarni birlashtiradigan VIEW yaratishingiz mumkin, garchi bu ma'lumotlar ma'lumotlar bazasida alohida jadvallarda saqlangan bo'lsa ham

<hr>

- ### Kamchilik

  **Samaradorlik uchun qo'shimcha yuk**: VIEW ba'zan samaradorlik muammolariga olib kelishi mumkin, ayniqsa ular birlashmalar, quyi so'rovlar yoki yig'ishlarni o'z ichiga olgan murakkab so'rovlar ustiga qurilgan bo'lsa. VIEW aslida saqlangan so'rov bo'lgani uchun har safar VIEW ga kirganingizda ma'lumotlar bazasi asosiy so'rovni bajarishi kerak

  **Jismoniy jihatdan saqlanmaydi**: An'anaviy VIEW (materiallashtirilmagan) hech qanday ma'lumotni saqlamaydi. Ular faqat mavjud jadvallarda ishlaydigan saqlangan so'rovlardir. Shu sababli, agar asosiy ma'lumotlar so'rov uchun katta yoki murakkab bo'lsa, VIEW har bir kirishda qayta hisoblash kerakligi sababli samaradorlik yomonlashishi mumkin

  **O'gartirish cheklovlari**: Barcha VIEW lar ham yangilanmaydi va bajarilishi mumkin bo'lgan yangilanish turlari bo'yicha cheklovlar mavjud. Masalan, guruhlash, agregatlar, DISTINCT va hokazolarni o'z ichiga olgan VIEW larni odatda to'g'ridan-to'g'ri yangilab bo'lmaydi.

  **Potentsial xavfsizlik xavflari**: VIEW lar ma'lum ma'lumotlarni yashirish orqali xavfsizlikni kuchaytirishi mumkin bo'lsa-da, agar ular to'g'ri ishlab chiqilmagan bo'lsa, ular beixtiyor maxfiy ma'lumotlarni oshkor qilishi mumkin

  **Bog'liqlik muammolari**: VIEW lar asosiy jadvallar va boshqa VIEW larga bog'liq. Agar VIEW bog'liq bo'lgan jadval o'zgartirilsa yoki o'chirilsa, u muammo hal etilmaguncha VIEW ni yaroqsiz holga keltirishi mumkin.

<hr>

- ### Example for **VIEW**

  ```SQL
  CREATE TABLE Books (
    BookID INT PRIMARY KEY,
    Title VARCHAR(100),
    Author VARCHAR(100),
    Genre VARCHAR(50),
    Price DECIMAL(5, 2)
  );

  INSERT INTO Books (BookID, Title, Author, Genre, Price) VALUES
    (1, 'To Kill a Mockingbird', 'Harper Lee', 'Classic', 18.99),
    (2, '1984', 'George Orwell', 'Dystopian', 15.99),
    (3, 'The Great Gatsby', 'F. Scott Fitzgerald', 'Novel', 20.99);

  CREATE VIEW BookSummary AS
  SELECT Title, Author, Genre
  FROM Books;
  ```

  Bu yerda **Books** nomli jadvaldan ma'lumot oluvchi **BookSummart** sodda shakldagi queryni o'z ichiga oluvchi VIEW ini yaratdik. Ushbu VIEW bizga 'Title', 'Author', 'Genre' columnlari bo'yicha ma'lumot oladi

  <hr>

- ### Note

> Shuni ta'kidlash kerakki, VIEW ma'lumotlarni o'zi saqlamaydi; ular shunchaki so'rov natijasini ifodalash usulini taqdim etadilar. VIEW orqali asosiy ma'lumotlarga kiritilgan har qanday o'zgarishlar asosiy jadvallardagi haqiqiy ma'lumotlarga ta'sir qiladi. Bundan tashqari, agar ular murakkab operatsiyalar, agregatlar yoki bir nechta jadvallarni o'z ichiga olsa, ba'zi VIEW yangilanmasligi mumkin.

> Databasedagi barcha VIEW larning ro'yxatini olish uchun:

```SQL
SHOW FULL TABLES IN your_db_name WHERE TABLE_TYPE LIKE 'VIEW';
```

<hr>

- ### Summary

<hr>

- [Main Page](https://github.com/Al1yev/my-wiki/tree/main)
