## null, undefined, undeclared
### undefiend
- 접근 가능한 스코프에 변수가 선언되었으나 현재 아무런 값도 할당되지 않은 상태

```
let test;
console.log(test); // undefined
console.log(typeof test); // undefined
```

### undeclared
- 접근 가능한 스코프에 변수 선언조차 되어있지 않은 상태

```
console.log(test2);

// 오류를 뱉어낸다.
// Uncaught ReferenceError: test2 is not defined at <anonymous>:1:13

console.log(typeof test2); // undefined
```

### null
- null이라는 빈 값을 할당하면 해당 변수의 타입은 객체가 된다.

```
let test3; // 변수 선언
test3 = null; // 선언한 변수 test3에 null 값 할당
console.log(test3); // null
console.log(typeof test3); // 변수 test3의 타입은 object 객체
```


결국, undefined와 null의 차이점은 

undefined는 타입이 결정되지않은 변수이고,

null은 타입은 객체며, 비어있는 변수이다.
