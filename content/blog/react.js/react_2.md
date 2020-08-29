---
title: ⚛ ②react component
date: 2020-08-29 16:08:02
category: react.js
draft: false
---

> 노마드코더의 [**ReactJS로 영화 웹 서비스 만들기**](https://nomadcoders.co/react-fundamentals/lobby)를 보면서 공부 중

## Component?

`component`는 `HTML`을 반환하는 함수인데, `react`는 기본적으로 이 `component`와 함께 동작한다.
`component`를 사용할 때엔 아래와 같은 방식으로 작성한다.

```javascript
ReactDOM.render(<App />, document.getElementById('root'))
```

`<App />`가 한 개의 컴포넌트.  
컴포넌트를 작성할 때엔 첫글자가 무조건 대문자로 작성되어야한다. 또 하나의 `js`파일 안에 두개 이상의 컴포넌트를 사용할 수 없다. `react`가 render할 수 없기 때문이다. 한개의 `js`파일엔 한개의 `component`만을 사용해야한다.  
해당 컴포넌트의 내용은 아래와 같다.

```javascript
import React from 'react'

function App() {
  return <h1>Hello world!</h1>
}

export default App
```

> jsx
>
> `jsx`는 `javaScript`와 `HTML`의 조합이다. 리액트에서만 사용하는 유일한 개념이다. 위와 같이 컴포넌트를 사용할 때 작성하는 방식이 `jsx`이다.

## Component 만들기

`component` 파일을 시작할 때엔 상단에 아래를 꼭 써줘야한다.

```javascript
import React from 'react'
```

이를 작성하지 않으면 `react`는 `jsx`가 있는 `component`를 사용하는 것을 이해하지 못한다.

`function`을 작성할 땐 함수명도 대문자로 시작해야한다. 마지막엔 아래와 같이 작성한다.

```javascript
export default 함수명
```

## Property

`props(=property)`는 `component`에 정보를 주는 방법이다.

예를 들어

```javascript
<Food fav="kimchi" />
```

위에서 `fav`가 `props`이다. 이 `props`을 가져오려면

```javascript
Component(props.fav) 또는 Component({ fav })
```

의 방법을 이용하면 된다.

`props`을 이용해서 동적 컴포넌트를 만들 수 있다.

```javascript
import React from 'react'
import ReactDOM from 'react-dom'
import App from './App'

ReactDOM.render(<App />, document.getElementById('root'))
```

```javascript
function Food({ fav }) {
  return <h1>I like {fav}</h1>
}

function App() {
  return (
    <div>
      <Food fav="kimchi" />
      <Food fav="samgyeopsal" />
      <Food fav="zzuccumi" />
    </div>
  )
}
```

결과는 아래와 같다.

```
I like kimchi
I like samgyeopsal
I like zzuccumi
```

<br><br>
`ES6`의 메서드인 `map()`를 사용할 수도 있다.
`map()`메서드는 `array`의 아이템들 각각에 함수를 취해 `array`를 반환한다

```javascript
import React from 'react'
import ReactDOM from 'react-dom'
import App from './App'

ReactDOM.render(<App />, document.getElementById('root'))
```

```javascript
import React from 'react'

function Food({ name }) {
  return <h1>I like {name}</h1>
}

const fruitList = [{ name: 'apple' }, { name: 'melon' }, { name: 'cherry' }]

function App() {
  return (
    <div>
      {fruitList.map(fruit => (
        <Food name={fruit.name} />
      ))}
    </div>
  )
}

export default App
```

```
I like apple
I like melon
I like cherry
```
