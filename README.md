## Theme

- ### What is Trigger

  SQL-dagi trigger - bu ma'lum bir jadval yoki ma'lumotlar bazasidagi ko'rinishdagi ma'lum hodisalarga javoban avtomatik ravishda bajariladigan maxsus turdagi saqlangan protsedura yoki tartibdir. Triggerlar, birinchi navbatda, ma'lumotlar bazasidagi ma'lumotlarning yaxlitligini saqlash va biznesning ma'lum qoidalarini avtomatik ravishda amalga oshirish uchun ishlatiladi

<hr>

- ### Syntax

  ```
  CREATE TRIGGER [trigger_name]
  [BEFORE | AFTER] [INSERT | UPDATE | DELETE]
  ON [table_name]
  [FOR EACH ROW]
  [trigger_body]
  ```

  CREATE TRIGGER [trigger_name]: Mavjud triggerni yaratadi yoki trigger_name bilan almashtiradi;
  [BEFORE | AFTER]: Bu trigger qachon bajarilishini bildiradi;
  [INSERT | UPDATE | DELETE]: Bu DML operatsiyasini belgilaydi;
  ON [table_name]: Bu trigger bilan bog'langan jadval nomini belgilaydi;
  [FOR EACH ROW]: Bu satr darajasidagi triggerni belgilaydi, ya'ni trigger har bir qator uchun bajariladi;
  [trigger_body]: Bu trigger ishga tushirilganda bajarilishi kerak bo'lgan operatsiyani ta'minlaydi.

<hr>

- ### Why should we use Trigger

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
