# TypeScript (타입스크립트)



## 타입스크립트 소개 

- 2021년 마이크로 소프트가 발표
- 자바스크립트를 기반으로 정적타입 문법을 추가한 프로그래밍 언어 

- 기존 자바스크립트는 별로 정리 안된 느낌 : 잘 정리되기 위해선 패턴 사용하면 되지만 패턴 공부해야하고 노력해야함
- 관리하기 쉽고 작업하기 쉬운 코드를 타입스크립트를 통해 할 수 있다.
- 타입스크립트를 사용하면 자바스크립트로 개발할때보다 버그를 줄이고, 쉬운 유지보수, 질 좋은 코드를 짤 수 있다.



## 타입스크립트를 알려면?

자바스크립트의 기초지식이 필요





## 타입스크립트란 ?  

### TypeScript is Superset of JavaScript

: 자바스크립트를 기반으로 한 언어 

![](https://github.com/jewdri-kim/typescript/blob/master/KakaoTalk_20210912_104941118.png)

-> 타입스크립트는 자바스크립트를 보다 쉽게 강력하게 작성하도록 도와주는 좀 더 나은 버전이 자바스크립트

### 타입스크립트의 특징

#### Type annotations (타입표기)

-  변수값에 데이터 타입 지정가능

  - 타입표기하면 코드 예측가능하고 디버깅하기 쉽다.

    ```javascript
    //Javascript
    function add(a, b){
        return a+b;
    }
    
    console.log(add('3','5'));
    ```

    ```typescript
    //typescript
    function add(a: number, b: number){
        return a+b;
    }
    
    console.log(add('3','5'));   // 실행되기전 컴파일 오류!!
    ```

    

#### Object Oriented feature (객체지향적)

- 클래스, 인터페이스, 컨스트럭터, 퍼블릭, 프라이빗 등과 같은 객체지향 특성을 지원한다. 
- 객체지향 개념 : https://github.com/jewdri-kim/OOAD/blob/master/99_java/5%EC%9E%A5%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D.md



#### 컴파일 타임 오류

- 컴파일시 나타나는 오류 
- 브라우저는 타입스크립트 코드를 이해하지 못함 (브라우저는 자바스크립트)
- 타입스크립트로 작성된 코드 ---> 컴파일 ----> 자바스크립트
- 타입스크립트 : 프로그래밍 언어인 동시에 컴파일러! 타입스크립트를 자바스크립트로 !

#### 



# 타입스크립트 설치와 개발환경 



1. #### Visual Studio 설치

2. ####  타입스크립트 (TypeScript) 설치 

   1. https://www.typescriptlang.org/
   2. npm : Node Package Manager -> node js 의 한부분
   3. typescript 사용하기 위해서 node js 설치

   ![](https://github.com/jewdri-kim/typescript/blob/master/install.png)

3. #### 타입스크립트 파일 만들기



## 타입스크립트로 파일 작성 및 실행해보기

![](https://github.com/jewdri-kim/typescript/blob/master/compile.png)

1. #### 파일작성

   ```typescript
   //app.ts
   function logName(name: string){
       console.log(name);
   }
   
   logName('Jewdri');
   ```

   

2. #### 컴파일 및 실행

   ```cmd
   cd 경로
   
   tsc app.ts
   ```

   - 터미널에서 실행

   ![](https://github.com/jewdri-kim/typescript/blob/master/8.png)

   ```
   node app.js
   ```

   - watch

   ![](https://github.com/jewdri-kim/typescript/blob/master/watcher.png)

   ```
   tsc -w app.ts
   ```

   - 컴파일 타임시 오류

   ```typescript
   //app.ts
   function logName(name: string){
       console.log(name);
   }
   
   logName(3333);
   ```

   ![](https://github.com/jewdri-kim/typescript/blob/master/error.png)

   - 디버깅이 편하다
   - 실행 전 미리 오류 잡을 수 있다. 

   

3. #### 버그?

   ![](https://github.com/jewdri-kim/typescript/blob/master/7.png)

   ![](https://github.com/jewdri-kim/typescript/blob/master/INIT.png)

   ```
   tsc --init
   ```





# 타입스크립트 기본문법 



## 기본타입

Boolean, Number, String, Object, Array, Tuple, Enum, Any, Void, Null, Undefined, Never



### 변수에 타입설정

```typescript
let str:string = 'hi';
let num:number = 100;

let arr:Array = [1, 2, 3];
let arr2:number[] = [1, 2, 3];

let obj:object = {};
let obj2:{name: string, age:number} = {
    name;'Jewdri'
    age:36
}
```

### 

### 함수에 타입 설정

```typescript
function add(a:number, b:number){
    return a+b;
}
```



### 기본타입 중 자바스크립트에 존재하지 않는 타입



#### Tuple : 배열의 타입순서와 배열 길이를 지정할 수 있는 타입

```typescript
var arr:[string, number] = ['aa', 100];
```

#### Enum 

-  Number 또는 String 값 집합에 고정된 이름을 부여할 수 있는 타입
- 값의 종류가 일정한 범위로 정해져 있는 경우에 유용
- 기본적으로 0부터 시작하며 값은 1씩 증가

```typescript
enum Shoes {
    Nike = '나이키',
    Adidas = '아디다스'
}
```

#### Any : 모든 데이터 타입 허용

#### Void 

- 변수에는 undefined와 null만 할당
- 함수에는 리턴값을 설정할 수 없는 타입

#### Never : 특정 값이 절대 발생할 수 없을때 사용



### 인터페이스

인터페이스는 타입을 정의한 규칙을 의미

```typescript
interface User{
    age: number;
    name: string;
}
```

```typescript
//변수와 함수에 활용
var person:User ={
    age: 30,
    name: 'Jewdri'
}

function getUser(user:user){
    console.log(user);
}
```

```typescript
//인덱싱 
interface StringArray{
    [index:number]:string;
}

var arr2:StringArray=['a','b','c'];
arr[0] = 10 //Error;
```

```typescript
//딕셔너리 패턴
interface StringRegexDictionary{
	[key: string]:RegExp
}

var obj:StringRegexDictionary = {
    cssFile:/\.css$/,
    jsFile: 'a' //Error
}

obj['cssFile'] = /\.css$/;
obj['jsFile'] = 'a';  //Error
```

```typescript
//인터페이스 확장
interface Person{
    name: string;
    age: number;
}

interface User extends Person{
    language: string; 
}
```







### 타입추론

 : 타입스크립트에서는 타입표기가 없는 경우 여러분의 코드를 읽고 분석하여 타입을 유추

```typescript
let a = 10;
a = 5;
a = 'aaa';
```

