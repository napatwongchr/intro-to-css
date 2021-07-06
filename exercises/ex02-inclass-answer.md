# EX02 In Class Answer

จาก code

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

อันดับแรกเราจะคำนวน specificity ของแต่ละ selectors ก่อน

**อย่าลืมหลักการนับ specificity นะ**

- tag ได้ 1 แต้ม
- class ได้ 10 แต้ม
- id ได้ 100 แต้ม

เรามาเริ่มนับ selectors ที่เกี่ยวข้องกับ post title

- `h1.post-title` มี specificity 1 + 10 = 11 แต้ม
- `.post-title` มี specificity 10 แต้ม
- `.post-title.post-title` มี specificity 10 + 10 = 20 แต้ม

เพราะฉะนั้น post-title จะมีสี slateblue และขนาด font เป็น 50px เนื่องจากคุณสมบัติ cascading

ต่อไปเรามานับ selectors ที่เกี่ยวข้องกับ post content

- `.post-content` มี specificity 10 + 10 = 10 แต้ม
- `.post-content.post-content.post-content` มี specificity 10 + 10 + 10 = 30 แต้ม
- `p.post-content.post-content.post-content` มี specificity 1 + 10 + 10 + 10 = 31 แต้ม

เพราะฉะนั้น post-content จะมีสี goldenrod และขนาด font เป็น 40px เนื่องจากคุณสมบัติ cascading
