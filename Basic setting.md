# tsconfig.json 기본 설정

## Targets

```tsx
{
  "include": ["src"],
  "compilerOptions": {
    "outDir": "build",
    "target": "ES6",
  }
}
```

- `outDir` 은 `ts` 파일에서 `js`  파일로 컴파일 될 때 생성될 풀더의 이름을 설정할 수 있다.
- `target` 컴파일될 때 js 파일의 문법 수준을 설정할 수 있다. // es6 가 보편적임으로 추천됨

## Lib Configuration

- 라이브러리들(modul)을 정의
- 정의된 타겟의 실행환경을 나타냄

```tsx
{
  "include": ["src"],
  "compilerOptions": {
    "outDir": "build",
    "target": "ES6",
		"lib": ["ES6" , "DOM"] // es6 지원하는 서버와 DOM, 즉 브라우저 환경에서 코드를 실행시킨다는 의미
  }
}
```

- `lib` 에 `ES6` 를 추가함으로서 es6 문법을 기본 유형으로 정의함
- `DOM` 의 의미는 브라우저 환경에서 코드가 실행될 것임으로 정의함
    - 브라우저 환경에서 코드가 실행될 것임을 정의했음으로, `window.` or `document.` 등을 사용할 수 있음
    - 브라우저에서 사용 가능한 기능들의 타입이  정의된 `lib.dom.d.ts` 을 사용할 수 있기 때문
    

## JSDoc

- js 와 ts 파일이 섞여 있는 모듈을 사용할 경우 js 파일을 그대로 사용할 수 있는 방법 중 하나
- js 파일에서 간단하게 코멘트를 추가해 type 을 정의할 수 있음

```tsx
// @ts-check
/**
 * Initializes the project
 * @param {object} config
 * @param {boolean} config.debug
 * @param {string} config.url
 * @returns boolean
 */
export function init(config) {
  return true;
}

/**
 * Exits the program
 * @param {number} code
 * @returns number
 */
export function exit(code) {
  return code + 1;
}
```

- 위와 같이 코멘트를 통해 js 파일에서 ts 의 보호기능을 사용할 수 있음

```tsx
{
  "include": ["src"],
  "compilerOptions": {
    "outDir": "build",
    "target": "ES6",
		"lib": ["ES6" , "DOM"]
		"strict": true, // strict 모드에선 js 모듈 파일이 허용되지 않음
    "allowJs": true // allowJs 를 통해 js 파일을 사용할 수 있음
  }
}
```
