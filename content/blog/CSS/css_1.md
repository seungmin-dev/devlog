---
title: 🎨CSS Flexbox
date: 2020-09-27 14:04:49
category: CSS
draft: false
---

> 노마드코더의 [**CSS 마스터 클래스**](https://nomadcoders.co/css-layout-masterclass)를 보면서 공부 중

## Flexbox

```css
display: flex;
```

### Axis

`flex-direction: row`(default)일 때 `main axis`는 `horizontal`, `cross axis`는 `vertical`
반대로 `fle-direction: column`일 때 `main axis`는 `vertical`, `cross axis`는 `horizontal`

### `display: flex`가 적용된 요소에 주는 속성

```css
justify-content: space-between;
(default)align-content: space-between;
```

### 자식요소에게 줄 수 있는 속성

- `align-self` ➡ cross-axis로 적용 `center`, `flex-end` (부모요소에 height이 있어야만 작동, `flex-direction`에 상관없이 적용) == `align-items`
- `order` ➡ css로 요소의 순서 바꾸기. 기본값은 0. 1로 지정하면 한자리씩 밀려난다.
- `flex-wrap` ➡ 기본값은 nowrap, wrap하면 지정된 자식요소의 크기를 보존한다. nowrap은 크기 변형시키면서 한 줄에 가득 채운다.
  > > flex-direction: row-reverse 한 줄의 요소들 순서 앞뒤바뀜, column-reverse. flex-wrap: wrap-reverse
- `align-content` ➡ 각 자식요소들간의 공백 제어. (`flex-start`- 공백을 없앤다, `center` - 모든 요소들이 상위 요소의 한 가운데, `space-between` `space-around`(default))
- `flex-shrink` ➡ default : 1; 반응형에서 2 이상으로 설정하면 브라우저 사이즈가 줄어들 때 다른 요소들보다 선택요소가 배수만큼 줄어든다.
- `flex-grow` ➡ shrink랑 반대. default는 0. 공백을 잡아먹기도 하고 커질 수 있을만큼 커진다.
- `flex-basis` ➡ **main-axis**에서 적용. flex 속성 지정 전에 초기 width를 지정해야한다.
