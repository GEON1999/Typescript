# Interface

## 1. Interface vs Type Aliases

```tsx
interface Person {
	name: string,
	age: number
}
```

```tsx
type Person = {
	name: string,
	age: number
}

// 아래와 같이도 가능함

type Name = string;
type Age = number;

type Person = {
	name : Name,
	age : Age
}
```

1. `interface` 는 오브젝트만 타입만을 정의할 수 있음
2. `type` 은 `interface` 보다 훨씬 유연하게 사용 가능
    1. `concrete type` 혹은 `concrete value` 만을 정의할 수도 있음
    

## 2. extand

```tsx
interface User {
	name: string
}

interface Player extends User {
	age: number
}
```

```tsx
type User = {
	name: string
}

type Player = User & {
	age: number
}
```

- 위 예제코드와 같이 확장하는 방식이 다름

## 3. **overlap**

```tsx
interface User {
	name: string
}

interface User {
	nickName: string
}

interface User {
	age: number
}
```

```tsx
type User {
	name: string
}

type User {
	nickName: string
}

// 중복이 불가능함
```

- `interfcae` 는 중복된 이름으로  선언되고 자동으로 합쳐지지만, `type` 은 불가능 함
