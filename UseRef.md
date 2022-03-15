> ### useRef


useRef คือ React Hooks ที่สามารถเข้าถึงโดยการ Reference ไปที่ DOM element ใช้กับ Functional component สามารถทำ initialValue (.current) ได้ ตามตัวอย่าง

```
import { useRef } from "react";
import ReactDOM from "react-dom";

function App() {
  const inputElement = useRef();

  const focusInput = () => {
    inputElement.current.focus();
  };

  return (
    <>
      <input type="text" ref={inputElement} />
      <button onClick={focusInput}>Focus Input</button>
    </>
  );
}

ReactDOM.render(<App />, document.getElementById('root'));
```



