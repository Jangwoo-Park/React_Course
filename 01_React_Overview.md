

프론트엔드 미니 부트캠프나 실제 프로젝트에 바로 활용할 수 있게 **핵심 개념 → 동작 원리 → 필수 문법 → 고급 개념 → 생태계** 순서로 설명

---

# 📌 React 정리

## 1. React란?

* **UI 라이브러리**: Facebook(현재 Meta)에서 개발한 **컴포넌트 기반** JavaScript 라이브러리.
* 목적: **재사용 가능한 컴포넌트**를 통해 웹 애플리케이션의 UI를 효율적으로 구성.
* 특징: **선언형(Declarative)**, **컴포넌트 기반(Component-based)**, **Virtual DOM** 활용.

---

## 2. React의 동작 원리

1. **Virtual DOM**

   * 실제 DOM을 직접 조작하지 않고, 가상 DOM에 변경사항을 반영 후 비교(Diffing).
   * 바뀐 부분만 실제 DOM에 적용(효율적인 업데이트 → 성능 최적화).

2. **컴포넌트 기반 아키텍처**

   * UI를 작은 단위(컴포넌트)로 쪼개서 관리.
   * 재사용 가능 + 유지보수 용이.

3. **단방향 데이터 흐름**

   * 상위 → 하위 컴포넌트로 props 전달.
   * 예측 가능한 상태 관리 가능.

---

## 3. React의 기본 문법

### (1) 컴포넌트

* 함수형 컴포넌트 (권장)

```jsx
function Hello({ name }) {
  return <h1>Hello, {name}!</h1>;
}
```

* 클래스형 컴포넌트 (이제는 거의 사용 X)

```jsx
class Hello extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}
```

---

### (2) JSX

* JavaScript + XML 문법
* HTML처럼 보이지만 실제로는 `React.createElement()` 호출로 변환됨.

```jsx
const element = <h1 className="title">Hello React</h1>;
```

---

### (3) Props와 State

* **Props**: 부모 → 자식 전달, 읽기 전용
* **State**: 컴포넌트 내부에서 관리하는 동적 데이터

```jsx
function Counter() {
  const [count, setCount] = React.useState(0);
  return (
    <>
      <p>{count}</p>
      <button onClick={() => setCount(count + 1)}>+</button>
    </>
  );
}
```

---

### (4) 이벤트 처리

```jsx
<button onClick={() => alert("Clicked!")}>Click Me</button>
```

---

### (5) 조건부 렌더링

```jsx
{isLoggedIn ? <Dashboard /> : <Login />}
```

---

### (6) 리스트 렌더링

```jsx
const items = ["apple", "banana", "cherry"];
<ul>
  {items.map((item, index) => (
    <li key={index}>{item}</li>
  ))}
</ul>
```

---

## 4. 고급 개념

1. **Hooks**

   * `useState`, `useEffect`, `useContext`, `useReducer`, `useMemo`, `useCallback`
   * 클래스 없이도 상태/라이프사이클 관리 가능.

2. **Context API**

   * 전역 상태 공유 (ex. 다크모드, 로그인 정보).

3. **React Router**

   * SPA(Single Page Application)에서 페이지 이동 구현.

4. **상태 관리 라이브러리**

   * Redux, Zustand, Recoil, Jotai 등.

5. **성능 최적화**

   * React.memo, useMemo, useCallback → 불필요한 렌더링 방지.

---

## 5. React 생태계

* **빌드 툴**: Vite, CRA(Create React App) → 요즘은 Vite 선호
* **스타일링**: CSS Modules, Styled-components, Tailwind CSS
* **상태 관리**: Redux Toolkit, Recoil, Zustand
* **서버 연동**: Axios, React Query, SWR
* **SSR/SSG 프레임워크**: Next.js (SEO, 성능 최적화)

---

## 6. React의 장단점

✅ 장점

* 컴포넌트 재사용 → 유지보수성 ↑
* Virtual DOM → 빠른 렌더링
* 방대한 생태계와 커뮤니티 지원
* 선언형 프로그래밍 → 가독성 ↑

⚠️ 단점

* 러닝 커브 (JSX, Hooks, 상태 관리)
* 빠르게 변화하는 생태계 → 최신 트렌드 추적 필요
* SEO 최적화는 SSR(Next.js) 없이는 제한적

---

👉 정리하면:
React는 **UI 개발을 위한 표준급 라이브러리**이고, 현대 프론트엔드 개발에서는 **Next.js + React + Tailwind + Zustand/React Query** 조합이 사실상 대세입니다.

---


