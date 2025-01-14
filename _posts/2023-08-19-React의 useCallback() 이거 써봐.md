---
title: React의 useCallback() 이거 써봐
date: 2023-08-19 20:00:00 +0900
categories:
  - React
tags:
  - useCallback
---

안녕하세요! 오늘은 아주아주 중요한 주제로 찾아왔어요. React를 사용하면서 `useCallback()`이라는 훅에 대해 아십니까? `useState`나 `useEffect`도 좋지만, `useCallback`도 반드시 알아야 할 중요한 친구입니다! 😉

## 함수 메모이제이션 🌍

먼저 이 `useCallback`이 뭐냐고요? 간단하게 말하자면, 함수를 기억하게 해주는 훅이에요. 😎 컴포넌트가 다시 그려질 때마다 함수를 새로 만들면 굉장히 비효율적이거든요.

```javascript
const memoizedCallback = useCallback(함수, 배열);
```

이런 식으로 쓰면, 배열 안의 값이 바뀌지 않는 한 같은 함수를 계속 쓸 수 있어요! 🎉

## 자바스크립트에서의 함수 동등성 문제 💡

자바스크립트에서 함수는 객체로 취급되기 때문에, 동등성 비교는 메모리 주소를 기반으로 해요. 그래서 같은 코드의 함수도 `===`로 비교하면 `false`가 나와버리는 거죠!

그래서 이게 왜 중요하냐고요? 함수를 다른 함수나 컴포넌트에게 전달할 때, 이 동등성 문제 때문에 성능 문제가 발생할 수 있어요.

## useCallback과 useEffect의 환상의 콤비 💫

`useEffect` 같은 경우도, 의존 배열이 바뀌지 않으면 함수를 다시 호출하지 않아요. 그런데 여기서 문제가 생겨요! 함수는 컴포넌트가 랜더링될 때마다 새로운 참조값으로 변경되니까요. 그래서 이런 문제를 피하려면 `useCallback`을 써서 함수의 참조값을 일정하게 유지시키는 거죠!

## React.memo와 함께 쓰면 더 좋아 🌟

`React.memo()`는 뭐냐고요? 이것도 역시 성능 최적화에 도움을 주는 친구입니다. `useCallback()`과 함께 쓰면 자식 컴포넌트의 불필요한 랜더링을 줄일 수 있어요! 🙌

---

오늘은 이렇게 `useCallback`에 대해서 알아봤어요! 이제 이 친구를 적극 활용해서 앱을 더 빠르게 만들어보아요! 🚀🚀🚀

재미있게 읽어주셔서 감사합니다! 😊👏
