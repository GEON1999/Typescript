# 타입스크립트의 존재 이유

1. 에러 방지
    
    ```jsx
    function sum(a, b) {
      return a + b;
    }
    
    sum(10, 20); // 30
    sum('10', '20'); // 1020
    ```
    
    ```tsx
    function sum(a: number, b: number) {
      return a + b;
    }
    
    sum(10, 20); // 30
    sum('10', '20'); // Error: '10'은 number에 할당될 수 없습니다.
    ```
    
    - 의도치 않은 타입의 사용으로 의도치 않은 결과를 사전에 방지할 수 있음

1. 생산성
    
    ```tsx
    function sum(a: number, b: number): number {
      return a + b;
    }
    var total = sum(10, 20);
    total.toLocaleString();
    ```
    
    - Visual studio 를 만든 MS 에서 Typescript 를 만들었기 때문에 개발에 최적화 되어있다.
    - 위 코드와의 경우, `argument` 들의 `type` 이 `number` 이며 `return` 값 또한 `number` 이다. 그럼으로 `total`의 값은 `number` 이 되며 해당 타입에 대한 API 를 미리보기할 수 있음
    - 이외에도 `fetch` 등을 통해 얻는 data 에 대해 `type` 을 정의 해두면 자동완성 기능을 사용할 수 있어 편리함
        - ex) [https://github.com/GEON1999/carrot-market/blob/main/pages/index.tsx](https://github.com/GEON1999/carrot-market/blob/main/pages/index.tsx)
