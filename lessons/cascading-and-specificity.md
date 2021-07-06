# Cascading and Specificity

Cascade แปลว่า **"ไหลลงมา"**

ถ้ามีการเขียน selector ที่เหมือนกัน **properties ของ selector ตัวสุดท้าย** จะเป็นตัวที่ใช้แสดงผล

ลองมาดูตัวอย่าง code

```html
<h1 class="welcome-text">Welcome To Alcodemist Coding School</h1>

<style>
  .welcome-text {
    color: crimson;
    font-size: 90px;
  }
  .welcome-text {
    color: skyblue;
  }
</style>
```

- ลองตอบหน่อยว่า ข้อความ "Welcome To Alcodemist Coding School" จะแสดงผลเป็นสีอะไร ?
- จากคุณสมบัติ cascading ถ้ามีการเขียน selector ที่เหมือนกัน **properties ของ selector ตัวสุดท้าย** จะเป็นตัวที่ใช้แสดงผล เพราะฉะนั้นข้อความจะแสดงผลเป็นสี skyblue

## Multi Selectors

เนื่องจากว่าเราสามารถกําหนด class ได้มากกว่า 1 และเราสามารถเขียน selectors ได้มากกว่า 1 selectors

ยกตัวอย่างเช่น

```html
<h1 class="welcome-text branding-text">Welcome To Alcodemist Coding School</h1>
<style>
  .welcome-text.branding-text {
    color: crimson;
    font-size: 90px;
  }
  .welcome-text {
    color: skyblue;
  }
</style>
```

- ลองตอบหน่อยว่า ข้อความ "Welcome To Alcodemist Coding School" จะแสดงผลเป็นสีอะไร ?
- จากคุณสมบัติ cascading ถ้ามีการเขียน selector ที่เหมือนกัน **properties ของ selector ตัวสุดท้าย** จะเป็นตัวที่ใช้แสดงผล เพราะฉะนั้นข้อความน่าจะแสดงผลเป็นสี skyblue
- แต่มันไม่เป็นอย่างนั้นข้อความจะแสดงผลเป็นสี crimson เนื่องจากเรามี selector `.welcome-text.branding-text` ที่ select ทั้ง welcome-text และ branding-text **มันทำให้มีความเจาะจงมากกว่า (Specificity)** select welcome-text อย่างเดียว

## Specificity

Specificity คือ ค่าความจําเพาะเจาะจง

หลักการคิด Specificity คือ ให้นับแต้ม selectors ที่แต้มเยอะสุดจะได้ใช้แสดงผล

- tag ได้ 1 แต้ม
- class ได้ 10 แต้ม
- id ได้ 100 แต้ม

ถ้าลองคำนวน specificity จาก code ด้านบนจะได้ว่า

```html
<h1 class="welcome-text branding-text">Welcome To Alcodemist Coding School</h1>
<style>
  .welcome-text.branding-text {
    /* Specificity 10 + 10 = 20 แต้ม */
    color: crimson;
    font-size: 90px;
  }
  .welcome-text {
    /* Specificity 10 แต้ม */
    color: skyblue;
  }
</style>
```

- ลองมาดู specificity ของ selector `.welcome-text.branding-text`
  - .welcome-text ได้ 10 แต้ม เนื่องจาก select ด้วย class ได้ 10 แต้ม
  - .branding-text ได้อีก 10 แต้ม
  - รวมทั้งหมด 20 แต้ม
- ต่อมา specificity ของ selector `.welcome-text`
  - .welcome-text อย่างเดียว 10 แต้ม

## In Class Exercises - 02 🏅

จาก code ด้านล่าง ให้ลองตอบว่า post title, และpost content ตัวข้อความจะมีสีอะไร และขนาดเท่าไหร่

```html
<div class="post">
  <h1 class="post-title">Post title</h1>
  <p class="post-content">
    post content: Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    Pellentesque vel est nec felis dignissim finibus. Aliquam sodales mollis
    odio, non aliquam quam eleifend ut. Morbi ante turpis, accumsan sed vehicula
    at, auctor vitae ante. Pellentesque ac consectetur justo. Vestibulum
    interdum tempus vestibulum. Nunc mattis, diam nec ultrices laoreet, ante leo
    ultrices purus, nec pulvinar odio magna a ex. Nam turpis odio, porttitor
    quis purus in, aliquet semper sem.
  </p>
</div>

<style>
  h1.post-title {
    color: palevioletred;
  }

  .post-title {
    color: sandybrown;
    font-size: 50px;
  }

  .post-title.post-title {
    color: slateblue;
  }

  .post-content {
    font-size: 40px;
  }

  .post-content.post-content.post-content {
    color: purple;
  }

  p.post-content.post-content.post-content {
    color: goldenrod;
  }
</style>
```

[Answer](https://github.com/napatwongchr/intro-to-html/blob/main/exercises/ex02-inclass-answer.md)
