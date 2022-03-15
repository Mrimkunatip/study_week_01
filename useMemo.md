> ### useMemo


หลักการของ useMemo คือการ Cache ข้อมูลไว้
- ถูกเรียกครั้งแรกเมื่อมีการ Render
- ถูกเรียกอีกครั้งเมื่อมีการ Re-Render และ ค่าใน Array deps มีการเปลี่ยนแปลง
- Return ออกเป็นค่า Value

```
useMemo() => {
  const [number, setNumber] = useState(0)
  const [someValue, setSomeValue] = useState(0)

  const getTimestamp = () => (new Date().getTime())
  
  const numberWithoutMemo = getTimestamp()

  const getNumberWithMemo = useMemo(() => {
    return getTimestamp()
  }, [someValue])

  return (
    <>
      <p>แบบไม่ใช้ useMemo: {numberWithoutMemo}</p>
      <hr />
      <p>แบบใช้ useMemo: {getNumberWithMemo}</p>
      <hr />
      ทดลองเปลี่ยนค่า (Number): {number}<br/>
      <button onClick={() => { setNumber((prev) => ++prev) }}>เพิ่ม (+)</button>
      <button onClick={() => { setNumber((prev) => --prev) }}>ลด (-)</button>
      <hr />
      ทดลองเปลี่ยนค่า (Some value): {someValue}<br />
      <button onClick={() => { setSomeValue((prev) => ++prev) }}>เพิ่ม (+)</button>
      <button onClick={() => { setSomeValue((prev) => --prev) }}>ลด (-)</button>
    </>
  )
}
```