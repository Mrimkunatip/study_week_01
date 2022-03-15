
> ### Git

  หลักการทำงานของ git คือ เป็นแหล่งรวบรม โปรเจค ต่างๆ หรือการทำ version control คือเราสามารถย้อนกลับไปทำงานในเวอร์ชั่นเก่าได้
  ข้อดีของมันคือมันสามารถบอกถึงระดับการเปลี่ยนแปลงของของโค้ดที่ละเอียดมาก ตัวอย่างการใช้งาน git https://www.youtube.com/watch?v=5TlGWHU_SQc&t=917s
  
  ![](https://cdn-ssl-devio-img.classmethod.jp/wp-content/uploads/2021/06/git-flow-model-640x848.png)
 
  ในรูปหลักการทำงาน ของ git จำเป็นต้อง clone project ลงบน local ของเครื่องตัวเองก่อน จากนั้นให้เราสร้าง New Branch จาก Branch master หรือ จาก Branch developer
  ตามรูปด้านบน ซะก่อน การสร้างแบบนี้เพื่อไม่ให้ Branch หลัก เสียหาย จึงจำเป็นต้องสร้าง Branch ของตัวเองขึ้นมา ตามตัวอย่างรูปด้านบน
  
  ![](https://miro.medium.com/max/602/1*OqKfKe3mqCRbaWT2Y8YDOQ.png)
  
  ในการใช้งาน จำเป็นต้องรู้สิ่งนี้ด้วยคือ Git Life Cycle จากรู้เห็นได้ว่าแบ่งเป็น 2 ส่วน ฝั่งที่เป็น Local Repository และ Remote 
  ฝั่ง Local Repository นี้คือฝั่งบนเครื่องของเรา ที่ clone มาจาก ฝั่ง Remote ในการแก้ไขจะไม่ถูกแก้ไขในฝั่ง Remote ทันที่เลยแต่จะมีขั้นตอนการต่่างๆก่อน เริ่มแรก จาก state Working ก่อน ว่าตอนนี้เราทำงานอยู่ที่ folder ไหนก่อน หรือ file นั้น
  ใน state แรกจำมีคำสั่ง Git add ก่อน เพื่อให้ file ที่มีการเปลี่ยนแปลงนั้นไปอยู่บน staging Area ก่อน ว่าเป็นบอกกับตัว git ว่าจะมีการเปลี่ยนแปลง จากนั้นก็จะทำการ commit จาก staging Area ไปที่ Repository เพื่อเป็นการเตรียมพร้อมอีกครั้งจากนั้นค่อย git push ขึ้นไปบน ฝั่ง Remote หรือบน github นั้นเอง 
