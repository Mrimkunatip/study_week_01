#### Week_01


> ### Stateless and Statefull

  Stateless คือการสร้าง Component ที่เราสร้างขึ้นมาใช้งานไม่จําเป็นจะต้องใช้ State อาจเป็นเพียง Component ที่รับข้อมูลเข้ามาแล้วแสดงผลเพียงอย่างเดียว เช่น
  ตัวอย่างการใช้งาน Stateless component https://www.youtube.com/watch?v=Wz4JZeVKbuA
```
import React from 'react'

function header(props) {
    return (
        <div>
            <h1>{props.msg}</h1>
        </div>
    )
}

export default header

<!-- Function header จะรับค่า Props เข้ามา แล้ว Return JSX ออกไป โดยใช้ props.msg ตาม props ที่ส่งมา -->
```
  stateful คือการสร้าง
  
  <hr />

> ### Git

  หลักการทำงานของ git คือ เป็นแหล่งรวบรม โปรเจค ต่างๆ หรือการทำ version control คือเราสามารถย้อนกลับไปทำงานในเวอร์ชั่นเก่าได้
  ข้อดีของมันคือมันสามารถบอกถึงระดับการเปลี่ยนแปลงของของโค้ดที่ละเอียดมาก ตัวอย่างการใช้งาน git https://www.youtube.com/watch?v=5TlGWHU_SQc&t=917s
 


<hr />

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
  
  
<hr />

> Next.js
อ่านเพิ่มเติม https://nextjs.org/docs/getting-started


<hr />

> high order component


<hr />
