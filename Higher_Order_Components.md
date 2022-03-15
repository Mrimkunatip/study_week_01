> ### Higher Order Components

Higher Order Components คือ การ share logic ระหว่าง component หรือเป็นการเรียกใช้ logic แบบซ้ำๆ โดยจะเป็น function ที่ใช้ รับ parameter เป็น component และ returns ออกมาเป็น component ใหม่ เช่น

จากตัวอย่างจะเห็นว่า class ทั้ง 2 ตัว ต้องการข้อมูลจาก API เหมือนกัน จึงทำให้เราเรียกใช้ API บ่อยจนเกิดไป

```
class Aticles extends Component {
  state = {
    articles: [],
  }

  componentDidMount() {
    fetch('/api/v1/articles')
      .then((res) => res.json())
      .then((articles) => this.setState({ articles }))
  }

  render() {
    return (
      <ul>
        {this.state.articles.map(({ id, title }) => (
          <li key={id}>{title}</li>
        ))}
      </ul>
    )
  }
}
```

```
class Users extends Component {
  state = {
    users: [],
  }

  componentDidMount() {
    fetch('/api/v1/users')
      .then((res) => res.json())
      .then((articles) => this.setState({ users }))
  }

  render() {
    return (
      <ul>
        {this.state.users.map(({ id, name }) => (
          <li key={id}>{name}</li>
        ))}
      </ul>
    )
  }
}
```

> เทคนิคที่ช่วยแก้ปัญหานี้

```
class Aticles extends Component {
  render() {
    return (
      <ul>
        {this.props.data.map(({ id, title }) => (
          <li key={id}>{title}</li>
        ))}
      </ul>
    )
  }
}

export default withFetch('/api/v1/articles')(Articles)

// users.js
class Users extends Component {
  render() {
    return (
      <ul>
        {this.props.data.map(({ id, name }) => (
          <li key={id}>{name}</li>
        ))}
      </ul>
    )
  }
}
export default withFetch('/api/v1/users')(Users)
```
withFetch ทำให้เราละโค้ดส่วนการประกาศ state และการร้องขอข้อมูลจาก API ออกไปได้ เหลือเพียงการเรียกใช้งานฟังก์ชันดังกล่าวพร้อมระบุ URL ที่ต้องการจะเข้าถึงข้อมูลจากเซิฟเวอร์ก็จะตอบกลับมาเป็นค่าของ data ภายใต้ props ของคอมโพแนนท์นั่นเอง

```
const withFetch = (url) => (WrappedComponent) =>
  class extends Component {
    state = {
      data: null,
    }

    componentDidMount() {
      fetch(url)
        .then((res) => res.json())
        .then((data) => this.setState({ data }))
    }

    render() {
      return <WrappedComponent {...this.props} {...this.state} />
    }
  }
```



