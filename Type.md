# Type

### String

```tsx
let str: string = "hi";
```

### Number

```tsx
let num: number = 10;
```

### Boolean

```tsx
let isLoggedIn: boolean = false;
```

### Array

```tsx
let arr: number[] = [1, 2, 3];
```

### Tuple

```tsx
let arr: [string, number] = ["hi", 10];
```

- 튜플은 배열의 길이가 고정되고 각 요소의 타입이 지정되어 있는 배열 형식을 의미함

### Any

```tsx
let str: any = "hi";
let num: any = 10;
let arr: any = ["a", 2, true];
```

- 타입스크립트를 점진적으로 적용할 때 활용 가능
- 단어 의미 그대로 모든 타입을 허용

### Void

```tsx
let unuseful: void = undefined;
function notuse(): void {
  console.log("sth");
}
```

- 반환 값을 설정할 수 없는 타입

### Never

```tsx
function neverEnd(): never {
  throw new Error("error");
}
```

- 절대 함수의 끝가지 도달할 수 없는 타입

### Unkown

```tsx
let a: unknown;

if (typeof a === `number`) {
  let b = a + 1;
}
```

- 매개변수의 값을 미리알 수 없을 때 사용할 수 있음

### Enum
- 특정 값(상수)들의 집합을 의미합니다.
```
enum Avengers { Capt = 2, IronMan, Thor }
let hero: Avengers = Avengers[2]; // Capt
let hero: Avengers = Avengers[4]; // Thor
```
