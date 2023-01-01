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
  
* 접근하려는 프로퍼티가 표현식이나 예약어일 경우 대괄호 표기법만을 사용해야 한다.  
    
example
```javascript
foo['full-name'] = 'foo bar';      // '-' 연산자가 있는 표현식
console.log(foo.['full-name']);    // foo bar
console.log(foo.full-name);        // NaN (수치 연산을 해서 정상적인 값을 얻지 못할 때 출력되는 값)
```

