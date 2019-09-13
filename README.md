<div align="center">

# 리액트 Context API([Nomad Coders](https://academy.nomadcoders.co/p/antiredux-new-react-context-api))

Learning how you will be able to use the new Context API to replace redux in your small or medium React projects and how you can manage local state without going insane.

</div>

## Goal

- **understanding**: Context API 이론, 기본지식
- **making**: 간단한 시뮬레이션

</br>

## Curriculum

- [x] [#1 Introduction](https://github.com/sweetmilkys/nc-contextapi/commit/022394b718a9965537e0e7555772d7f854bfa4f1)
- [x] [#2 Setup](https://github.com/sweetmilkys/nc-contextapi/commit/82904c392e52231bceae6862b9947ccab2cfd604)
- [x] [#3 Creating the Store](https://github.com/sweetmilkys/nc-contextapi/commit/ee0408fe5bb634d6ffd90d2fe751585d775c92c7)
- [x] [#4 Consuming the Store](https://github.com/sweetmilkys/nc-contextapi/commit/7619dc26d141843afce086823bc8e2a69cc16382)
- [x] [#5 Updating the Store](https://github.com/sweetmilkys/nc-contextapi/commit/f25e06d1eb0608b189b4037ff3ef23791eb8858a)
- [x] [#6 Rendering the Notifications](https://github.com/sweetmilkys/nc-contextapi/commit/2bcf48f88cbb927c232836f201ba62204a25eb2d)
- [x] [#7 Counting Unseen Notifications]()
- [ ] [#8 Deleting and Seeing Notifications]()
- [ ] [#9 Conclusions]()

</br>

## Stack

- React

</br>

## Libray

- [styled-components](https://www.styled-components.com/docs)  
  Visual primitives for the component age. Use the best bits of ES6 and CSS to style your apps without stress

  ```
  yarn add styled-components
  ```

- [styled-reset](https://github.com/zacanger/styled-reset#readme)  
  Reset CSS for styled-components

  ```
  yarn add styled-reset
  ```

- [styled-flex-component](https://github.com/SaraVieira/styled-flex-component#readme)  
  Flex Element for not writing any more custom flex styles because fuck that

  ```
  yarn add styled-flex-component
  ```

- [typography](https://github.com/KyleAMathews/typography.js)  
  A powerful toolkit for building websites with beautiful typography.

  ```
  yarn add typography
  ```

- [react-fontawesome](https://github.com/FortAwesome/react-fontawesome)
  Font Awesome 5 React component

```
yarn add react-fontawesome
```

</br>

## Reference

- [React v16.3.0: New lifecycles and context API](https://reactjs.org/blog/2018/03/29/react-v-16-3.html)
- [Context](https://reactjs.org/docs/context.html)

## Note

### Context

Context는 단계마다 일일이 props를 전달하지 않고도 컴포넌트 트리 전체에 데이터를 제공할 수 있음

### 언제 context를 써야할까?

다양한 레벨에 걸쳐 컴포넌트에 데이터 값이 변할 때마다 모든 하위 컴포넌트에게 데이터를 전달해야할 때  
단, context를 사용하면 컴포넌트 재사용하기 어려워지므로 꼭 필요할 때만 사용하도록 함(컴포넌트 합성이 context 사용할 때보다 더 좋은 경우도 있음)

### API

- React.createContext: Context 객체를 만듬

  ```JS
  const MyContext = React.createContext(defaultValue);
  ```

- Context.Provider: value prop를 받아 이 값을 하위에 있는 컴포넌트에게 전달

  ```JS
  <MyContext.Provider value={/* 어떤 값 */}>
  ```

- Context.Consumer: 함수 컴포넌트안에서 context를 읽기 위해서 사용  
  자식은 함수여야 함

  ```JS
  <MyContext.Consumer>
    {value => /* context 값을 이용한 렌더링 */}
  </MyContext.Consumer>
  ```

### 하위 컴포넌트에서 context 업데이트
컴포넌트 트리 하위 깊숙이 있는 컴포넌트에서 context를 업데이트 하려면 context를 통해 매서드를 전달.  
**반드시 Provider에 포함시킬 함수는 construct에 있어야 함**
