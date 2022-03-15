> ### useCallback

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