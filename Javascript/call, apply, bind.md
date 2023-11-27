## Call, Apply, Bind의 차이점
### Call
- Call() 모든 함수에서 사용가능하며, this를 특정 객체로 지정할 수 있다.
- function.call(thisArg[, arg1[, arg2[, ...]]])
  - thisArg: function 호출에 제공되는 this의 값
  - arg1, arg2,... function이 호출되어야 하는 인수
- 첫 번째 매개변수 thisArg는 각 함수의 실행문맥의 this를 특정하게 지정하는 매개변수임을 알 수 있다. 그리고 두 번째부터는 호출할 함수의 인수들이 들어간다.
- 메서드의 호출 주체인 함수를 즉시 실행하는 메서드이다.

```
let person = {
  name: 'kevin';
}

let person2 = {
  name: 'martin',
  study: function() {
    console.log(this.name + '이 공부하고 있다');
  }
}

person2.study(); // Kim이 공부하고 있다.
person2.study.call(person); // kevin이 공부하고 있다.
```

### Apply
- apply()는 call()과 유사하지만, 매개변수 처리 방법에서 차이가 있다.
- call()은 일반적인 함수처럼 매개변수를 받지만, apply()는 배열형태의 매개변수를 받는다.
- fun.apply(thisArg, [argsArray])
  - thisArg: fnuc 호출에 제공되는 this의 값
  - argsArray: func이 호출되어야 하는 인수를 지정하는 유사 배열 객체
- 첫 번째 매개변수 thisArg는 Function.prototype.call()과 같이 this를 지정한다. 하지만 call()과 다르게 apply()는 두 번째 매개변수를 배열 형태로 넣게된다는 차이점이 있다.
- apply도 call과 동일하게 메서드의 호출 주체인 함수를 즉시 실행하나 차이점은 첫번째 인자 이후의 인자들을 배열로 받는다는 것이다.

### Bind
- bind()는 커스텀 this를 가리키는 함수를 생성할 수 있게 해준다.
- func.bind(thisArg[, arg1[, arg2[, ...]]])
  - thisArg: 바인딩 함수가 타겟 함수의 this에 전달하는 값
  - arg1, arg2, ...func이 호출되어야 하는 인수
- bind()는 새롭게 바인딩한 함수를 만든다. 바인딩한 함수는 원본 함수 객체를 감싸는 함수이다.
- bind()는 call(), apply()와 같이 함수가 가리키고 있는 this를 바꾸지만 호출되지는 않는다. 따라서 변수를 할당하여 호출하는 형태로 사용된다.
- 함수를 즉시 실행하지 않고 넘겨 받은 인수를 바탕으로 새로운 함수를 반환하는 메서드이다.

```
let person1 = {
    name: 'kevin'
};

let person2 = {
    name: 'martin',
    study: function() {
        console.log(this.name + '이 공부를 하고 있습니다.');
    }
};

person2.study(); // kevin이 공부를 하고 있습니다.

// bind()
let student = person2.study.bind(person1);

student(); // martin이 공부를 하고 있습니다.
```
