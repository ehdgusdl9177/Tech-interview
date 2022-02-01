## 콜백 지옥(Callback Hell)
- 콜백 지옥이란 콜백 함수를 익명 함수로 전달하는 과정에서 또 다시 콜백 안에 함수 호출이 반복되어 코드의 들여쓰기 수준이 감당하기 힘들 정도로 깊어지는 현상을 말한다.
- 주로 이벤트 처리나 서버 통신과 같은 비동기 작업을 제어하기 위해서 사용되는데 이러한 프로그래밍은 가독성이 떨어지고 코드 수정을 어렵게 한다.
- 자바스크립트는 비동기 프로그램이라는 특성상 이벤트에 따라 받는 콜백이 복잡해지면 내부에서 지속적으로 콜백을 사용하게 되므로 코드 읽기가 아주 어려워지는 상황이 발생하게 된다. 이러한 상황을 콜백 지옥이라고 한다.

### 콜백 지옥 탈출
#### 1. Promise
- ES6의 Promise를 이용할 수 있다.
- Promise는 new 연산자와 함께 호출하고 인자로 콜백을 받는다.
- Promise는 Promise를 반환한다.
- Promise는 호출될 때 바로 실행되지만 그 안에 콜백은 resolve, reject 둘 중 하나가 호출되기 전에 then 또는 catch로 넘어가지 않는다.
- resolve, reject로 성공 혹은 실패로 결과 값을 나타내어 다음 작업을 체이닝 할 수 있다.(즉, 비동기 제어가 가능하다.)
- then으로 작업을 이어가기 위해서는 resolve() 함수를 호출한다.
- 작업을 중단 혹은 err 처리를 위해서는 reject() 함수를 호출한다.
- 예를 들면 서버에서 데이터를 받아올 때 받아오기에 성공할 경우 resolve() 함수를 호출하고 실패할 경우 reject() 함수를 호출해서 서로 다른 작업으로 이어질 수 있게 만들 수 있다.

```
// Promise 기본 패턴 1 : 성공인 경우
function fn() {
  new Promise((resolve, reject) => {
    console.log('하나');
    // 실패인 경우 reject() 함수를 호출하면 된다.
    // 그러면 then()을 건너뛰고 catch()가 실행된다.
    resolve(); 
  })
  .then(() => {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        console.log('둘');
        resolve();
      }, 0);
    });
  })
  .then(() => {
    console.log('셋');
  })
  .catch((err) => {
    console.log('err ', err);
  });
}
```

#### 2. Promise + async/await
- ES2017에서 추가된 async/await 문법을 이용한 방법이 있다.
- Promise로 비동기 처리를 하더라도 콜백 지옥이 연상되는 것을 알 수 있었다.(then 안에 Promise 안에 then 안에 Promise 안에...)
- 비동기 작업을 수행하고자 하는 함수 앞에 async를 표기하고, 함수 내부에서 실질적인 비동기 작업이 필요한 위치마다 await를 표기하는 것만으로 뒤의 내용을 Promise로 자동 전환하고 해당 내용이 resolve된 이후에야 다음으로 진행된다.

```
// 중요 포인트 1 : return을 하지 않았어도 자동으로 fn함수는 Promise를 return 한다.
// 중요 포인트 2 : await을 붙이 Promise는 Promise를 리턴하지 않는다. (resole에 인자로 전달한 데이터를 리턴한다.)
async function fn() {
  let text = '하나';
  text = text + await new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve('둘');
    }, 0);
  });
  text += '셋';
  console.log(text + '넷');
}
```

#### 3. Generator
- ES6의 Generator를 이용한 방법이 있다.
- function* () 이런 형식으로 작성된 함수가 Generator 함수이다. Generator 함수를 실행하면 Iterator가 반환되는데 Iterator는 next 메서드를 가지고 있다. 이 next 메서드를 호출하면 앞서 멈췄던 부분부터 시작해서 그 다음에 등장하는 yield에서 함수의 실행을 멈춘다.
- 따라서 비동기 작업이 완료되는 시점마다 next 메서드를 호출하면 Generator 함수 내부의 소스가 위에서부터 아래로 순차적으로 진행된다.

```
const addCoffee = (prevName, name) => {
  setTimeout(() => {
    coffeeMaker.next(prevName ? `${prevName}, ${name}` : name);
  }, 500);
};

const coffeeGenerator = function* () {
  const espresso = yield addCoffee('', 'Espresso');
  console.log(espresso);
  const americano = yield addCoffee(espresso, 'Americano');
  console.log(americano);
  const mocha = yield addCoffee(americano, 'Mocha');
  console.log(mocha);
  const latte = yield addCoffee(mocha, 'Latte');
  console.log(latte);
};

const coffeeMaker = coffeeGenerator();
coffeeMaker.next();
```
