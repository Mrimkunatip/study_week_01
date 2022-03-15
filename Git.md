
> ### Git

  หลักการทำงานของ git คือ เป็นแหล่งรวบรม โปรเจค ต่างๆ หรือการทำ version control คือเราสามารถย้อนกลับไปทำงานในเวอร์ชั่นเก่าได้
  ข้อดีของมันคือมันสามารถบอกถึงระดับการเปลี่ยนแปลงของของโค้ดที่ละเอียดมาก ตัวอย่างการใช้งาน git https://www.youtube.com/watch?v=5TlGWHU_SQc&t=917s
  
  ![](https://cdn-ssl-devio-img.classmethod.jp/wp-content/uploads/2021/06/git-flow-model-640x848.png)
 
  ในรูปหลักการทำงาน ของ git จำเป็นต้อง clone project ลงบน local ของเครื่องตัวเองก่อน จากนั้นให้เราสร้าง New Branch จาก Branch master หรือ จาก Branch developer
  ตามรูปด้านบน ซะก่อน การสร้างแบบนี้เพื่อไม่ให้ Branch หลัก เสียหาย จึงจำเป็นต้องสร้าง Branch ของตัวเองขึ้นมา ตามตัวอย่างรูปด้านบน
  
  ![](https://miro.medium.com/max/602/1*OqKfKe3mqCRbaWT2Y8YDOQ.png)
  
  ในการ add git จำเป็นต้องรู้สิ่งนี้ด้วยคือ Git Life Cycle จากรู้เห็นได้ว่าแบ่งเป็น 2 ส่วน ฝั่งที่เป็น Local Repository และ Remote 
  ฝั่ง Local Repository นี้คือฝั่งบนเครื่องของเรา ที่ clone มาจาก ฝั่ง Remote 
