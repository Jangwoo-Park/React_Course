
리액트(React)에서 \*\*컴포넌트(Component)\*\*는 핵심 개념 중 하나예요.

---

## 🔹 컴포넌트(Component)란?

* **UI를 독립적이고 재사용 가능한 조각으로 나눈 것**
* HTML, CSS, JavaScript(또는 로직)를 하나의 단위로 묶어서 관리
* 함수처럼 호출해서 여러 번 재사용 가능

---

## 🔹 컴포넌트 종류

1. **함수형 컴포넌트 (Function Component)**

   * 가장 많이 쓰이는 방식
   * 단순히 함수 형태로 정의
   * `props`를 받아서 JSX 반환
   * React Hooks(`useState`, `useEffect`)로 상태와 생명주기 관리 가능

   ```jsx
   function Hello(props) {
     return <h1>Hello, {props.name}!</h1>;
   }
   ```

2. **클래스형 컴포넌트 (Class Component)**

   * 옛날에 주로 사용됨
   * `render()` 메서드 필요
   * `state`와 라이프사이클 메서드(`componentDidMount`, `componentDidUpdate`) 사용

   ```jsx
   class Hello extends React.Component {
     render() {
       return <h1>Hello, {this.props.name}!</h1>;
     }
   }
   ```

---

## 🔹 Props와 State

* **Props (Properties)**

  * 부모 → 자식에게 전달되는 데이터 (읽기 전용)
  * 수정 불가능 (immutable)
  * 재사용성 증가
  * 예: `<Hello name="React" />` → `props.name = "React"`

* **State**

  * 컴포넌트 내부에서 관리하는 데이터 (변경 가능)
  * 값이 바뀌면 자동으로 리렌더링 발생

  ```jsx
  import { useState } from "react";

  function Counter() {
    const [count, setCount] = useState(0);
    return (
      <div>
        <p>현재 값: {count}</p>
        <button onClick={() => setCount(count + 1)}>증가</button>
      </div>
    );
  }
  ```

---

## 🔹 컴포넌트의 특징

1. **재사용성** → 한 번 만든 컴포넌트를 여러 곳에서 활용 가능
2. **독립성** → 각 컴포넌트는 독립적으로 관리 가능
3. **계층 구조** → 부모-자식 구조로 UI 구성
4. **선언적 UI** → 상태(State)가 변하면 UI가 알아서 갱신됨
5. **작게 쪼갤수록 좋음** → 유지보수성, 가독성 향상

---

## 🔹 컴포넌트 작성 Best Practice

✅ 하나의 컴포넌트는 한 가지 역할만 담당하도록 작게 나누기
✅ 이름은 **PascalCase** 사용 (`UserCard`, `TodoItem`)
✅ props 기본값은 `defaultProps` 또는 함수 파라미터 기본값 활용
✅ 반복되는 UI는 map 함수로 처리

---

👉 정리하면, 컴포넌트는 **리액트의 최소 단위이자 재사용 가능한 UI 블록**이고, **props와 state**를 통해 데이터를 주고받으며 UI를 동적으로 구성합니다.

---


