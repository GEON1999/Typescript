# Generics
> 제네릭은 C#, Java 등의 언어에서 재사용성이 높은 컴포넌트를 만들 때 자주 활용되는 특징입니다. 특히, 한가지 타입보다 여러 가지 타입에서 동작하는 컴포넌트를 생성하는데 사용됩니다.
> 

```tsx
type PrintAny = {
	(arr: number[]):void
	(arr: string[]):void
	(arr: boolean[]):void
}

const print: PrintAny = (arr) => {
	console.log(arr[0])
}

print([1, 2, 3, 4])
print(["a", "b", "c"])
print([true, false])
```

```tsx
type PrintAny = <T>(arr : T[]) => T;

const print: PrintAny = (arr) => {
	console.log(arr[0])
}

print([1, 2, 3, 4])
print(["a", "b", "c"])
print([true, false])
```

- 매개변수의 인수를 확인해 `type` 을 `<T>` 에 담음

```tsx
type PrintAny = (arr : any[]) => any;

const print: PrintAny = (arr) => {
	console.log(arr[0])
}

const a = print([1, 2, 3, 4])
print(["a", "b", "c"])
print([true, false])

a.toUpperCase() // error 발생하지 않음
```

- `any` 는 인수의 `tpye` 과 맞지않는 함수를 사용해도 `error` 를 발생시키지 않음
