## ES6(ECMAScript6)
- ECMAScrupt2015로도 알려져 있는 ECMAScript6는 ECMAScript 표준의 가장 최신 버전이다. ES6는 새로운 언어 기능이 포함된 주요 업데이트이며, 2009년도에 표준화된 ES5 이후로 언어 기능에 대한 첫 업데이트이기도 하다. 현재 주요 Javsscript 엔진들에서 ES6 기능들을 구현 중에 있다.
- ES6는 새로운 기능들을 포함하고 있다.
  - const and let
  - Arrow function(화살표 함수)
  - Template literals(템플릿 리터럴)
  - Default parameters(기본 매개 변수)
  - Array and Object destructing(배열 및 객체 비구조화)
  - Import and Export(가져오기 및 내보내기)
  - Promise(프로미스)
  - Rest parameter and Spread operator(나머지 매개 변수 및 확산 연산자)
  - Classes(클래스)

### const and let 
- const는 변수 선언을 위한 ES6의 새로운 키워드이다.
- const는 var 보다 강력하고 일단 사용되면 변수를 다시 할당할 수 없다. 즉, 객체와 함께 사용할 때를 제외하고는 변경 불가능한 변수이다.
- 변경 불가능한 값을 정의하려면 const를 키워드를 사용하여 상수로 사용하는 것이 좋다.
  ```
  const button = document.getElementById("button");
  ```
- let은 새로운 값을 받을 수도 있고 재할당할 수도 있다. 즉, 변경 가능한 변수가 생성된다.
  ```
  let name = 'kevin';
  name = 'dev';
  console.log(name); // 'dev'
  ```

### Arrow function(화살표 함수)
- 화살표 함수는 Javascript에서 함수를 정의하는 function 키워드 없이 함수를 만들 수 있으며, return 키워드 없이 식을 계산한 값이 자동으로 반환된다.
- ()안에 함수의 인자가 들어가고, => 오른쪽에는 결과를 반환하는 식이다.
  ```
  ES5
  function myFunc(name) {
    return 'myname is' + name;
  }
    
  ES6
  const myFunc = (name) => {
    return `myname is ${name}`;
  }
  
  or
  
  const myFunc = (name) => `myname is ${name}`;
  ```
  
### 
