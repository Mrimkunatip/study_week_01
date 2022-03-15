> ### Stateless and Statefull

Stateless คือการสร้าง Component ที่เราสร้างขึ้นมาใช้งานไม่จําเป็นจะต้องใช้ State อาจเป็นเพียง Component ที่แสดงผลเพียงอย่างเดียว เช่น

```
const BooksList = ({books}) => {
 return (
   <ul>
     {books.map(book => {
       return <li>book</li>
     })}
   </ul>
 )
}

export default header

<!-- Function header จะรับค่า Props เข้ามา แล้ว Return JSX ออกไป ตาม props ที่ส่งมา -->
```

stateful คือการสร้าง ตัวจัดการ state ในรูปแบบต่างๆ เช่น

```
  class Main extends Component {
    constructor() {
      super()
        this.state = {
     books: []
   }
 }
 render() {
   return <BooksList books={this.state.books} />;
 }
}
```
