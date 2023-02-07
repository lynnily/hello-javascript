# 『인사이드 자바스크립트』
송형주, 한빛미디어(2014)   

📝 2022/12/20 ~ ing   

## 1장 자바스크립트 기본 개요   

## 2장 자바스크립트 개발 환경   

### 2.3 테스트 및 디버깅
업데이트 이후 WebStorm에서 javascript의 실행 및 디버그는 항상 Chrome을 통해 열게 되었기 때문에 browser를 firefox로 선택할 수 없다. [(참조1)](https://intellij-support.jetbrains.com/hc/en-us/community/posts/115000493450-How-Do-I-Make-WebStorm-Use-Firefox-Developer-Edition-when-launching-debugger-) [(참조2)](https://www.jetbrains.com/help/webstorm/configuring-javascript-debugger.html)

## 3장 자바스크립트 데이터 타입과 연산자

### 3.1 자바스크립트 기본 타입
* 자바스크립트는 **느슨한 타입 체크 언어**이다.  
* `undefined`는 타입이자, 값을 나타낸다.
* `null`의 타입은 object이다.

### 3.2 자바스크립트 참조 타입(객체 타입)
* `객체` : **이름(key):값(value)** 형태의 프로퍼티들을 저장하는 컨테이너
* 객체는 여러 개의 프로퍼티들을 포함할 수 있다.
* `프로퍼티` : 객체 안에서 선언된 이름과 값으로 이루어진 한 쌍
* 프로퍼티는 기본 타입의 값을 포함하거나, 다른 객체를 가리킬 수도 있다.
* 프로퍼티의 값이 함수일 경우 **메서드**라고 한다.

example
```javascript
const person = {
  firstName: "Lynn",
  lastName: "Ha"
  age: 20
}

// 위의 예시에서 person은 객체이고 firstName은 프로퍼티 이름(key), "Lynn"은 프로퍼티 값(value)이다.
```  

### 3.2.1 객체 생성
1. **기본 제공 Object() 객체 생성자 함수**를 이용하는 방법
```javascript
var foo = new Object();

foo.name = 'foo';
foo.age = 30;
foo.gender = 'male';

console.log(typeof foo);  // object
console.log(foo);         // {name: 'foo', age: 30, gender: 'male'}
```
2. **객체 리터럴**을 이용하는 방법  
   - 리터럴 : 표기법  
   - 객체 리터럴 : 객체를 생성하는 표기법  
   - **중괄호 {}** 를 이용해서 객체를 생성한다.  
   - 중괄호 안에 **프로퍼티 이름:프로퍼티 값** 형태로 표기한다.
```javascript
var foo = {
  name : 'foo',
  age : 30,
  gender : 'male'
};

console.log(typeof foo);  // object
console.log(foo);         // {name: 'foo', age: 30, gender: 'male'}
```
3. **생성자 함수**를 이용하는 방법

### 3.2.2. 객체 프로퍼티 읽기/쓰기/갱신
* 대괄호([]) 표기법
```javascript
console.log(foo['name'])
foo['major'] = 'electronics engineering';
```

* 마침표(.) 표기법
```javascript
console.log(foo.name)
foo.major = 'electronics engineering';
```

* 접근하려는 프로퍼티가 표현식이나 예약어일 경우 **대괄호 표기법**만을 사용해야 한다.
```javascript
foo['full-name'] = 'foo bar';      // '-' 연산자가 있는 표현식
console.log(foo.['full-name']);    // foo bar
console.log(foo.full-name);        // NaN (수치 연산을 해서 정상적인 값을 얻지 못할 때 출력되는 값)
```

### 3.3 참조 타입의 특성

* `delete` 연산자는 객체의 프로퍼티를 삭제할 뿐, 객체 자체를 삭제하지 못한다.
* 객체의 모든 연산은 실제 값이 아닌 참조값으로 처리된다.

### 3.4 프로토타입
자바스크립트의 **모든 객체는 자신의 부모 역할을 하는 객체와 연결되어 있다.**  
부모 객체의 프로퍼티를 마치 자신의 것처럼 쓸 수 있다.(like 상속)  
이러한 부모 객체를 **프로토타입 객체**(줄여서 **프로토타입**)라고 부른다.  
모든 객체의 프로토타입은 객체를 생성할 때 결정된다.  
프로토타입 객체는 임의의 다른 객체로 변경 가능하다.

### 3.5 배열

### 3.7 연산자

* `+` : 더하기 연산(두 연산자가 모두 숫자일 경우만), 문자열 연결 연산 수행
* `typeof` : 피연산자 타입을 문자열 형태로 리턴

|타입|타입명|typeof 결과|
|---|---|---|
|기본타입|null|'object'|
|참조타입|배열|'object'|
|참조타입|함수|'function'|

* `==` 동등 연산자 : 비교하려는 피연산자의 타입이 다른 경우에 **타입 변환**을 거친 다음 비교
* `===` 일치 연산자 : 비교하려는 피연산자의 타입이 다른 경우에 **타입을 변경하지 않고** 비교
```javascript
console.log(1 == '1');   // true
console.log(1 === '1');  // false
```
* `!!` : 피연산자를 불린값으로 변환
