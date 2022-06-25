# JavaScript 공부하기

> [이 링크](https://learnjs.vlpt.us/basics/02-variables.html)에서 제공해주는 내용을 하나씩 하나씩 차례로 공부할 것임! 



### 1장. 자바스크립트 입문 Prologue

#### 01. Hello, JavaScript

- 자바스크립트는 따로 프로그램을 설치할 필요없이 브라우저의 개발자 도구 console 창에서 실행할 수 있음. 

  - `console.log('Hello, JavaSript!')`, `console.log(1+2+3)` 를 크롬 콘솔창(f12)에서 실행해보자.
- `console.log` 명령어는 console창에 입력된 내용을 띄움.
  - 브라우저에서 `about:blank`에 접속해서 실행하면 깔끔한 상태에서 시작할 수 있음.

  

- 그러나 매번 코드를 작성할 때마다 개발자 도구창에 접속하는 것은 불편함. 이때 활용 가능한 사이트가 있음! 바로 [CodeSandbox](https://codesandbox.io/dashboard/home?workspace=4b81ef1a-1849-486e-a4fe-b5d02b9c09a6)라는 사이트임. 코드를 작성하고 바로 결과물을 확인할 수 있다. 깃헙과도 연동할 수 있어서 유용한 듯. 

![image-20220621210416425](study01.assets/image-20220621210416425.png)

- 처음 오른쪽에 뜨는 창은 다음과 같이 위에는 흰페이지, 아래에 결과물이 출력되는 콘솔창이 있는데, 흰페이지는 HTML 결과물을 보여주므로 지금은 딱히 볼 필요가 없음. 아래 콘솔창 결과물이 더 중요.

![image-20220621210513077](study01.assets/image-20220621210513077.png)

- 이렇게 콘솔창탭을 옆에 위쪽에 끌어올려 옆에 추가해서 콘솔창만 띄워놓고 보는 것이 편함. 

  

##### \* 본격적으로 시작하기 전, 잠깐! : 주석처리에 대해

- 자바스크립트에서 한 줄 주석은 `//` 사용
- 여러 줄 주석 처리는 `/* (주석내용) */` 사용. 즉, `/*` 로 주석을 열고 `*/` 로 주석을 닫아주면 됨!



#### 02. 변수와 상수

- 변수와 상수는 특정 이름에 특정 값을 담을 때 사용.
  - 예) number 라는 이름에 1이라는 값을 넣는다고 가정해보자
  - `let number = 1;` 와 같이 코드를 작성하면 이제부터 콘솔창에 `number` 를 조회할 때(`console.log(number);`)마다 1의 값이 뜬다. 
- 이렇게 특정 이름에 특정 값을 설정하는 것을 __선언__이라 함. 



##### (1) 변수

- 변수는 가변적인 값을 말함. 한 번 선언된 뒤에도 바뀔 수 있다.

```javascript
let value = 1;
console.log(value); // 결과: 1
value = 7;
console.log(value); // 결과: 7
```

- 위와 같이 변수를 선언할 때에는 `let` 이라는 키워드를 사용함. 
- 주의할 점: __한 번 선언한 이름은 또 다시 똑같이 재활용하여 선언할 수 없다!__ 즉, 아래와 같은 코드는 오류가 발생한다. 

```javascript
let cookie = 5;
let cookie = 9;

SyntaxError: /src/index.js: Identifier 'cookie' has already been declared (16:4)
```

- 단, __다른 블록 범위 내에서는 동일한 이름을 사용 가능__하긴 함. 이에 대해서는 추후에~



##### (2) 상수 

- 상수는 한 번 선언되고 바뀌지 않는 값. 즉, **고정적임.** 

- 상수를 선언할 때에는 `const` 키워드를 사용

  - `const num = 1;`

- 다음과 같이 상수의 값을 바꾸려고 하면 오류가 발생.

  - ```javascript
    const num = 55;
    num = 60;
    
    TypeError: "num" is read-only
    ```

- 변수와 마찬가지로 한 번 선언된 이름을 재활용하여 선언할 수 없다!



##### \** 참고: 더이상 사용하지 않는 키워드, `var`

- 변수를 선언하는 또 다른 방법으로 `var`이라는 키워드가 존재. 그러나 더이상 사용하지 않는다. 
- `let` 키워드와의 주요 차이점은 똑같은 이름으로 여러 번 선언할 수 있다는 것. (+ `var`과 `let`은 사용할 수 있는 범위가 상이함)



##### (3) 데이터 타입

- 변수나 상수를 선언할 때, 숫자 외에도 다른 값들을 선언할 수 있다. 가장 기본적인 것부터 알아보자!

__1. 숫자 Number__

- 이미 위에서 사용해보았듯이 바로 값을 대입하여 사용.
- `let num = 10;`



__2. 문자열 String__

- 텍스트 형태의 값. 작은 따옴표 혹은 큰 따옴표로 감싸서 선언함.

- ```javascript
  let text = 'NCT127';
  let name = '마끄리';
  ```



__3. 참/거짓 Boolean__

- 흔히 bool 타입이라고 부르는 Boolean. 참 혹은 거짓 두 종류의 값만을 나타냄.

- ```javascript
  let sweets = true;
  let bitter = false;
  ```



__4. null과 undefined__

- 자바스크립트에서는 '없음'을 의미하는 데이터 타입이 두 종류 존재. 하나는 `null`이고 다른 하나는 `undefined`. 용도가 다름!

- `null`은 주로 이 값은 __'없다'고 선언__할 때 사용

  - ```javascript
    const homework = null;
    ```

- `undefined`는 __아직 설정되지 않았다__는 것을 의미

  - ```javascript
    let dream;
    console.log(dream);
    
    undefined
    ```

  - `dream`이라는 변수를 선언하긴 했지만, 값을 지정해주지는 않았기 때문에 console.log로 값을 띄운다면 undefined라고 뜨게 된다. 



















