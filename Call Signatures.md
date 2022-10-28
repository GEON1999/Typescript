# Call Signatures

```tsx
function sum(a: number, b: number) {
  return a + b;
}
```

```tsx
type Sum = (a: number, b: number) => number

function score: Sum (a, b) {
  return a + b;
}
```

- Call Signatures 를 통해 함수의 `type` 을 미리 선언해둘 수 있다.
- 첫 번째 코드 `Alias` 와의 차별화된 장점은 딱히 없는 듯 하다.
    - `return` 값을 지정한다는 차이점이 있지만, 매개변수의 `type` 을 지정하면 `return` 값 또한 추론할 수 있기 때문
