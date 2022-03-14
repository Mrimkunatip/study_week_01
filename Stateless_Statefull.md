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