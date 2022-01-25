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

### Arrow function (화살표 함수)
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
  
### Template Literals (템플릿 리터럴)
- 문자열을 연결하기 위해 더하기 (+) 연산자를 사용할 필요는 없으며, 백틱 (``)을 사용하여 문자열 내에서 변수를 사용할 수도  있다.
```
const myFunc = (name, age) => {
  return `myname is ${name} and my age is ${age}`;
}
```

### Default parameters (기본 매개 변수)
- 매개 변수를 쓰지 않는 경우 매개 변수가 이미 기본값에 정의되어 있으므로 정의되지 않은 오류가 반환되지 않는다. 따라서, 누락된 매개 변수를 사용하여 함수를 실행할 때 기본 매개 변수 t값을 사용하고 오류를 반환하지 않는다.

```
 const myFunc = (name, age) => {
  return `안녕 ${name} 너의 나이는 ${age}이니?`;
 }
 console.log(myFunc(케빈));
 // '안녕 케빈 너의 나이는 undefined 이니?'
```
- 위의 함수는 정의되지 않은 상태로 반환된다. 두 번째 매개 변수 age를 지정하는 것을 잊어버렸기 때문이다.
- 그러나 기본 매개 변수를 사용하면 정의되지 않은 매개 변수가 반환되자 않고 매개 변수 할당을 잊어버렸을 때 해당 값이 사용된다.

```
const myFunc = (name, age = 25) {
  return `안녕 ${name} 너의 나이는 ${age}이니?`;
}
 console.log(myFunc(케빈));
 // '안녕 케빈 너의 나이는 22 이니?'
```
- 두 번째 매개 변수를 놓쳤더라도 값을 반환한다. 이제 기본 파라미터를 사용하여 오류를 미리 처리할 수 있다.

### Array and Object destructing (배열 및 객체 비구조화)
- 비구조화를 통해 배열 또는 객체의 값을 새 변수에 더 쉽게 할당할 수 있다.
```
ES5
const user = {
  name: 'kevin',
  age: '25',
}
let name = user.name;
let age = user.age;
```

```
ES6
const user = {
  name: 'kevin',
  age: '25',
}
const { name, age } = user;
```

### Import and Export (가져오기 및 내보내기)
- Javascript 응용프로그램에서 import 및 export를 사용하면 성능이 향상된다. 이를 통해 별도의 재사용 가능한 구성요소를 작성할 수 있다.
- export를 사용하면 다른 Javascript 구성요소에 사용할 모듈을 내보낼 수 있다.
- 그 모듈을 우리의 컴포넌트에 사용하기 위해 가져오기 import를 사용한다.

```
export default function detail(name, age) {
  return `안녕 ${name}, 너의 나이는 ${age}살 이다`
}
```
```
import detail from './detailComponent'
console.log(detail(케빈, 25))
// '안녕 케빈, 너의 나이는 25살 이다.'
```
- 둘 이상의 모듈을 가져오려는 경우, 중괄호에 넣기만 하면 된다.

### Promise (프로미스)
- Promise는 ES6의 새로운 특징이며 비동기 코드를 쓰는 방법이다.
- 예를 들어 API에서 데이터를 가져오거나 실행하는데 시간이 걸리는 함수를 가지고 있을 때 사용할 수 있다.

```
const myPromise = () => {
  return new promise((reject, resolve)) => {
    resolve('성공적으로 Promise가 실행됬습니다')
  })
}
```
- Promise는 두 개의 매개 변수를 사용하며 resolve 및 reject 예상 오류를 처리할 수 있다.
- fetch 함수는 Promise 자체를 반환한다.

### Rest parameter and Spread opertator (나머지 매개 변수 및 확산 연산자)
- Rest parameter는 배열의 인수를 가져오고 새 배열을 반환하는데 사용된다.

```
const arr = ['케빈', '25', '반가워', '불타는 코딩', '파이팅'];

// 비구조화를 이용해 값을 얻기
const [ val1, val2, val3, ...rest ] = arr;

const func = (restOfArr) => {
  return restOfArr.filter((item) => {return item}).join(" ");
}

console.log(func(rest)) // '불타는 코딩 파이팅'
```

- Spread operator는 Rest parameter와 구문이 동일하지만 Spread operator는 인수뿐만 아니라 배열 자체를 가진다. for 반복문이나 다른 메서드를 사용하는 대신 Spread operator를 사용하여 배열의 값을 가져올 수 있다.

```
const arr = ['케빈', '25', '반가워', '불타는 코딩', '파이팅'];

const func = (...anArray) => {
  return anArray;
}

console.log(func(arr)); // ['케빈', '25', '반가워', '불타는 코딩', '파이팅'];
```

### Classes (클래스)
- class는 객체 지향 프로그래밍(OOP)의 핵심이다. 코드를 더욱 안전하게 캡슐화할 수 있다. class를 사용하면 코드 구조가 좋아지고 방향을 유지한다.

- class를 만들려면 class 키워드 뒤에 두 개의 중괄호가 있는 class 이름을 사용한다.
```
class myClass {
  constructor() {
  
  }
}
```

- new 키워드를 사용하여 class 메서드와 속성에 액세스할 수 있다.
```
class myClass {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}
const user = new myClass('케빈', 25)
console.log(user.name) // 케빈
console.log(user.age) // 25
```

- 다른 class에서 상속하려면 extends 키워드 다음에 상속할 class의 이름을 사용한다.
```
class myClass {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  sayHello() {
    console.log(`안녕 ${this.name} 너의 나이는 ${this.age}가 맞니?`)
  }
}

// myClass 메서드 및 속성 상속
Class UserProfile extends myClass {
  userName() {
    console.log(this.name)
  }
}

const profile = new UserProfile('케빈', 25);
profile.sayHello(); // 안녕 케빈 너의 나이는 25가 맞니?
profile.userName(); // 케빈
```
