> ### useReducers

UseReducer เป็นตัวช่วยในการจัดการ state ต่างๆ จะสร้างเป็น Function reducer ตามตัวอย่าง ในการใช้งานจะ มี state เริ่มต้น เเล้ว action ต่างๆ การเรียกใช้ useRedcer นั้น จะเหมือนการใช้งาน useState แต่ จะต้องส่ง function Reducer เข้าไปด้วย เช่น ในตัวอย่าง [const [todos, dispatch] = useReducer(reducer, initialTodos);] พอ function ไหนจะทำงานกับ state ก็จะ dispatch type เข้าไป เพื่อให้action นั้นเข้าไปทำงานใน function ตาม case ที่ action ตรงกัน 

```
import { useReducer } from "react";
import ReactDOM from "react-dom";

const initialTodos = [
  {
    id: 1,
    title: "Todo 1",
    complete: false,
  },
  {
    id: 2,
    title: "Todo 2",
    complete: false,
  },
];

const reducer = (state, action) => {
  switch (action.type) {
    case "COMPLETE":
      return state.map((todo) => {
        if (todo.id === action.id) {
          return { ...todo, complete: !todo.complete };
        } else {
          return todo;
        }
      });
    default:
      return state;
  }
};

function Todos() {
  const [todos, dispatch] = useReducer(reducer, initialTodos);

  const handleComplete = (todo) => {
    dispatch({ type: "COMPLETE", id: todo.id });
  };

  return (
    <>
      {todos.map((todo) => (
        <div key={todo.id}>
          <label>
            <input
              type="checkbox"
              checked={todo.complete}
              onChange={() => handleComplete(todo)}
            />
            {todo.title}
          </label>
        </div>
      ))}
    </>
  );
}

ReactDOM.render(<Todos />, document.getElementById('root'));
```