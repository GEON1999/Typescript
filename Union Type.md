# Union Type
- 유니온 타입이란 자바스크립의 OR(`||`) 연산자와 동일한 의미를 가짐
```
function contact(text: string | number) {
  // ...
}
```
- contact가 string 타입일 수도 number 타입일 수도 있다는 의미 
- 이처럼 `|` 연산자를 이용해 타입을 여러 개 연결하는 방식을 유니온 타입 정의 방식이라 함


## Union Type 의 장점
```
function getAge(age: any) {
  age.toFixe(); // 에러 발생, age의 타입이 any로 추론되기 때문에 숫자 관련된 API를 작성할 때 코드가 자동 완성되지 않는다.
  return age;
}

// 유니온 타입을 사용하는 경우
function getAge(age: number | string) {
  if (typeof age === 'number') {
    age.toFixed(); // 정상 동작, age의 타입이 `number`로 추론되기 때문에 숫자 관련된 API를 쉽게 자동완성 할 수 있다.
    return age;
  }
  if (typeof age === 'string') {
    return age;
  }
  return new TypeError('age must be number or string');
}

// 출처 - https://joshua1988.github.io/ts/guide/operator.html#union-type
```
- 위 코드 처럼 `any` 사용시 자동완성 되지 않지만, 유니온 타입 사용시 자동완성 기능을 사용할 수 있음
