# What is CSS

CSS เป็น **"กฏ"** ที่ เปลี่ยนสี, ลักษณะ, ตําแหน่งการจัดวางสิ่งของต่าง ๆ บนหน้าเว็บ

CSS ย่อมาจาก **C**ascading **S**tyle **S**heets Cascading แปลว่า **"การไหลลงมา"** ซึ่งเป็นคุณสมบัติอย่างหนึ่งของ CSS ซึ่งเราจะได้เรียนรู้ต่อไป

🌟 โครงสร้างสำคัญของ CSS ประกอบไปด้วย **Selectors** และ **Properties**

จากตัวอย่าง code

```html
<h1 class="welcome-text">Welcome To Alcodemist Coding School</h1>
<h2>Alcodemist is fabulous !</h2>

<style>
  .welcome-text {
    color: crimson;
  }

  h2 {
    color: lightcoral;
  }
</style>
```

- `.welcome-text` คือ selector ที่เอาไว้เลือก HTML Element ที่มี class ชื่อว่า `welcome-text` มาใส่กฎ หรือเรามักเรียกว่า "Properties" ในที่นี้เราบอกว่าให้มันมี property เป็น `color: crimson` ตัวอักษรก็จะเปลี่ยนเป็นสี crimson
- เช่นเดียวกันกับ `h2` คือ selector ที่เอาไว้เลือก HTML Element ที่มี tag h2 แล้วใส่ property เป็น `color: lightcoral` ตัวอักษรก็จะเปลี่ยนเป็นสี lightcoral
