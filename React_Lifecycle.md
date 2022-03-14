
> React Lifecycle

  life cycle ของ React ที่จะมี method ไว้ใช้ควบคุมการแสดงผลของ UI ตั้งแต่ก่อนแสดงผล (before render) หลังแสดงผล (after render) หรือการแสดงผลใหม่อีกรอบ (re-render)
  ว่าแต่ละ method มีหน้าที่ไว้ทำอะไร และเราควรหรือไม่ควรทำอะไรในแต่ละ method 
  1. Mounting หรือ First time render จะทำงานแค่ครั้งแรกของการ render ของ component นั้น
  
  ![](https://miro.medium.com/max/982/1*vVSpfUg9wuSVDGcB8uwzWQ.png)

  2. Updating หรือ re-render คือจะทำงานเมื่อเป็นการ re-render ไม่สามารถเรียกใช้งานขณะที่ first time render ได้ โดยแบ่งออกเป็น 2 life cycle คือ
  
    2.1 เมื่อ props change
  
   ![](https://miro.medium.com/max/678/1*A6Q5Sx9B7jJrXzxOgw8DIQ.png)
    
    2.2 เมื่อ state change
    
   ![](https://miro.medium.com/max/734/1*FvdSLcin5bkoSO2dKmwvAA.png)
   
   ตัวย่างการใช้งาน https://medium.com/@bigboss27051/react-life-cycle-%E0%B8%A1%E0%B8%B1%E0%B8%99%E0%B8%84%E0%B8%B7%E0%B8%AD%E0%B8%AD%E0%B8%B0%E0%B9%84%E0%B8%A3-4aff7affc6b5
  

