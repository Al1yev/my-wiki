## Theme

- ### What is Trigger

  SQL triggeri jadval bilan bog'langan ma'lumotlar bazasi ob'ekti bo'lib, ushbu jadvalda ma'lum bir hodisa sodir bo'lganda avtomatik ravishda SQL operatorlari to'plamini bajaradi. Triggerlar biznes qoidalarini qo'llash, ma'lumotlar yaxlitligini saqlash va ma'lumotlar bazasidagi muayyan harakatlarni avtomatlashtirish uchun ishlatiladi. Ular jadvalga ma'lumotlarni qo'shish, yangilash yoki o'chirish kabi turli hodisalar bilan qo'zg'alishi mumkin va ular ushbu hodisalar asosida qo'shimcha operatsiyalarni bajarishga imkon beradi.

  Triggerlarning 3 ta turi mavjud:

  1. **DDL Trigger**<br>
     _create_table_, _create_view_, _drop_table_, _drop_view_ va _alter_table_ kabi Data Definition Language (DDL) buyruqlari hisoblanib, ular bajarilganda DDL triggerlarining faollashishiga olib keladi.

     ```
      create tigger safety
      on database
      for
      create_table,alter_table,drop_table
      as
      print 'you can not create,drop and alter tab
     ```

  2. **DML Trigger**<br>
     INSERT, UPDATE va DELETE bilan boshlanadigan The Data uses Manipulation Language (DML) buyrug'i hodisalari _insert_table_, _update_view_ va _delete_table_ ga mos keladigan DML triggerlarini o'rnatadi.

     ```
      create trigger deep
      on emp
      for
      insert,update ,delete
      as
      print 'you can not insert,update and delete this table i'
      rollback;
     ```

  3. **Logon Trigger**<br>
     Tizimga kirish triggerlari LOGON hodisasiga javoban amal bajarish uchun ishlatilinadi. Autentifikatsiya jarayoni tugagandan so'ng, lekin foydalanuvchi sessiyasini o'rnatishdan oldin SQL Server namunasi bilan foydalanuvchi sessiyasi yaratilganda, LOGON hodisasi sodir bo'ladi. Natijada, PRINT bayonoti xabarlari va trigger tomonidan yaratilgan barcha xatolar SQL Server xatolar jurnalida ko'rinadi. Autentifikatsiya xatolari tizimga kirish triggerlaridan foydalanishga to'sqinlik qiladi. Ushbu triggerlar login faolligini kuzatish yoki server seanslarini tekshirish va boshqarish uchun maʼlum login ega boʻlishi mumkin boʻlgan seanslar soniga cheklov oʻrnatish uchun ishlatilishi mumkin.

<hr>

- ### Syntax

  ```
  CREATE TRIGGER [trigger_name]
  [BEFORE | AFTER] [INSERT | UPDATE | DELETE]
  ON [table_name]
  [FOR EACH ROW]
  [trigger_body]
  ```

  **CREATE TRIGGER [trigger_name]**: Mavjud triggerni yaratadi yoki 'trigger_name' bilan almashtiradi;<br>
  **[BEFORE | AFTER]**: Bu trigger qachon bajarilishini bildiradi;<br>
  **[INSERT | UPDATE | DELETE]**: Bu DML operatsiyasini belgilaydi;<br>
  **ON [table_name]**: Bu trigger bilan bog'langan jadval nomini belgilaydi;<br>
  **[FOR EACH ROW]**: Bu satr darajasidagi triggerni belgilaydi, ya'ni trigger har bir qator uchun bajariladi;<br>
  **[trigger_body]**: Bu trigger ishga tushirilganda bajarilishi kerak bo'lgan operatsiyani ta'minlaydi.

<hr>

- ### Why should we use Trigger

  **Ma'lumotlar yaxlitligi**: Triggerlar ma'lumotlar bazasi darajasida murakkab biznes qoidalari va cheklovlarini qo'llash imkonini beradi, bu esa ma'lumotlarning izchil va aniq bo'lishini ta'minlaydi.

  **Avtomatlashtirish**: Triggerlar ma'lum bir hodisa sodir bo'lganda oldindan belgilangan harakatlarni bajarish orqali takrorlanadigan yoki murakkab vazifalarni avtomatlashtirishi mumkin. Bu qo'lda aralashuvga bo'lgan ehtiyojni kamaytiradi va samaradorlikni oshiradi.

  **Audit izlari**: Triggerlar ma'lumotlarga kiritilgan o'zgarishlarni kuzatish uchun ishlatilishi mumkin, masalan, alohida audit jadvalidagi o'zgarishlarni qayd etish. Bu ma'lumotlar o'zgarishi tarixini tekshirish va saqlashga yordam beradi.

  **Ma'lumotlarni tekshirish**: Triggerlar ma'lumotlar bazasida faqat haqiqiy va mos ma'lumotlar saqlanishini ta'minlab, ma'lumotlarni kiritish, yangilash yoki o'chirishdan oldin qo'shimcha tekshiruvlarini amalga oshirishi mumkin.

<hr>

- ### When should we use Trigger

<hr>

- ### Kamchilik

<hr>

- ### Example for Trigger

  ```

  ```

<hr>

- ### Note

<hr>

- ### Summary

<hr>

- [Main Page](https://github.com/Al1yev/my-wiki/tree/main)
