> ### useCallback

หลักการของ useCallback คือการ Cache ฟังก์ชันไว้
- ไม่ ถูกเรียกเมื่อมีการ Render (จะถูกเรียกเมื่อเราสั่ง Call ฟังก์ชันเอง)
- ถูกเรียกอีกครั้งเมื่อสั่ง Call ฟังก์ชัน และ ค่าใน Array deps มีการเปลี่ยนแปลง
- Return ออกเป็น Function

```
() => {
  const [number, setNumber] = useState(0)
  const [someValue, setSomeValue] = useState(0)
  const [numberWithCallback, setNumberWithCallback] = useState(undefined)

  const getTimestamp = () => (new Date().getTime())
  
  const numberWithoutCallback = getTimestamp()

  const getNumber = useCallback(() => {
    setNumberWithCallback(() => getTimestamp())
  }, [someValue])
  
  return (
    <>
      <p>แบบไม่ใช้ useCallback: {numberWithoutCallback}</p>
      <hr />
      <p>แบบใช้ useCallback: {numberWithCallback}</p>
      <hr />
      ทดลองเปลี่ยนค่า (Number): {number}<br />
      <button onClick={() => { setNumber((prev) => ++prev) }}>เพิ่ม (+)</button>
      <button onClick={() => { setNumber((prev) => --prev) }}>ลด (-)</button>
      <hr />
      ทดลองเปลี่ยนค่า (Some value): {someValue}<br />
      <button onClick={() => { 
        setSomeValue((prev) => ++prev)
        getNumber()
      }}>เพิ่ม (+)</button>
      <button onClick={() => { 
        setSomeValue((prev) => --prev)
        getNumber()
      }}>ลด (-)</button>
    </>
  )
}
```