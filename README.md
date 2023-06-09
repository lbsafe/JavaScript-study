# JavaScript

<p align="center"><img src="https://user-images.githubusercontent.com/65703793/230275865-693a2a7b-0f87-4342-b05d-91a31bdecb4d.png" alt="js" width="150px"></p>

## JavaScript 에 대하여
>프로그래밍 언어로, 스크립트 언어에 해당된다. HTML, CSS와 함께 웹을 구성하는 요소 중 하나다. HTML이 웹 페이지의 기본 구조를 담당하고, CSS가 디자인을 담당한다면 **JavaScript는 웹 페이지가 사용자와 상호작용하여 동작하는 것을 담당**한다.
***

### 사용법
    
* **:one: Script 태그 사용**

    ```html
    <script>
        document.write('hello world');
    </script>
    <script>
        document.write(1+1);
    </script>
    ```
*  **:two: Console의 활용**
    ```js
    console.log('test');
    ```
    >개발자 도구(f12)를 통한 코드 수정 방법   
    :arrow_right: 간략한 테스트나 현재 웹페이지를 대상으로 사용할 수 있다.
***

## 데이터 타입

* **:one: 숫자 (Number)**
    * 정수형 10진수(일상생활 사용 숫자 소수점x)
    * 정수형 16진수
    * 실수형 (소수점을 갖는 숫자)

    ```html
    정수형: 33, 44
    정수형: (0x ~ 로 시작하여 0~9, A~F 로 모든 숫자 표현) ex) #f00 색상코드
    실수형: 50.5
    ```

* **:two: 문자열 (String)**
    * 일상생활 사용 글자

    ```html
    '1', "오건희", "hello"
    ```

* **:three: 논리형 (Boolean)**
    * true(참) or false(거짓)
    * true : 맞음, 1, 같음, 진실, 성공
    * false : 틀림, 0, 같지않음, 거짓, 실패

* **:four: undefined**   
    * 미정의된(초기화 되지 않은, 기본초기값), 들어오지 않은 자료형

    ```js
    ex1 : 
    var data1;
    alert('data1 =' + data1);

    ex2 :
    function exFunc(data1){
        alert("data1 = " + data1);
    }
    exFunc();
    ```

* **:five: null**

    * 아무것도 참조하지 않은 자료형 (객체를 담기위한 변수를 초기화 하는 상태)

    ```js
    ex :
    var data = null;
    ``` 

* :heavy_exclamation_mark: 이 외 **함수(function)**, **객체(object)** 등이 존재한다.
***

## 변수

> 변수(variable)는 하나의 값을 저장하기 위해 확보한 메모리 공간 자체 또는 그 메모리 공간을 식별하기 위해 붙인 이름이다.

* **:one: var**

    **(특징)**

    * 중복 선언 가능

    * 중복 선언으로 인한 문제점을 개선하기 위해 ES6부터 추가된 변수 선언 방식이 **let** 과 **const** 이다.

    **(단점)**

    * 기존에 선언해둔 변숫값을 제 할당하는 등의 실수가 발생할 가능성이 크다. 코드양이 많아졌을 때, 같은 이름의 변수명이 여러 번 선언되었다면 어디 부분에서 문제가 발생하는지 파악하기 힘들고 값이 바뀔 수 있다.

    **(예시)**

    ```js
    var name = 'lbsafe';
    console.log(name); // lbsafe

    var name = '오건희';
    console.log(name); // 오건희
    ```

* **:two: let**

    **(특징)**

    * 중복 선언 불가능, 재할당 가능

    * **var** 와 다르게 **let** 은 중복 선언이 불가능해서, 해당 변수가 선언 되면 에러 메시지가 출력된다.

    * **name = '오건희!'** 와 같이 변수 선언 및 초기화 이후 반복해서 다른 값을 재할당 할 수는 있음.

    **(예시)**

    ```js
    let name = 'lbsafe';
    console.log(name); // lbsafe

    let name = '오건희';
    console.log(name);
    // Uncaught SyntaxError: Identifier 'name' has already been declared

    name = '오건희!';
    console.log(name); // 오건희!
    ```

* **:three: const**

    **(특징)**

    * 중복 선언 불가능, 재할당 불가능

    * **let** 과 **const** 의 차이점은 **immutable** 의 여부이다. **let** 은 변수에 다른 값을 재할당 할 수 있지만, **const** 는 재할당 시 에러가 발생한다.

    * **const** 는 constant(상수)를 뜻하기 때문에 한 번만 선언이 가능하며 값을 바꿀 수도 없다. **(예시 2)** 와 같이 배열과 오브젝트의 값을 변경하는 것은 가능함.

    * **const** 는 불변을 의미하는 것과 다르게,   
    **값을 재할당하는 코드만 불가능**하다고 볼 수 있음.

    **(예시 1)**
    ```js
    const name = 'lbsafe';
    console.log(name); // lbsafe

    const name = '오건희';
    console.log(name);
    // Uncaught SyntaxError: Identifier 'name' has already been declared

    name = '오건희!';
    console.log(name);
    // Uncaught TypeError: Assignment to constant variable
    ```

    **(예시 2)**
    ```js
    function const_ex() {
        const list = ["A", "B", "C"]

        list = "D";
        console.log(list);
        // TypeError: Assignment to constant variable

        list.push("D");
        console.log(list); // ["A", "B", "C", "D"]
    }
    ```
***

## 연사자의 종류

* **:one: 산술 연산자**

    > 산술 연산자는 사칙연산을 다루는 가장 기본적인 연산자이다.   
    산술 연산자는 모두 두 개의 피연산자를 가지는 이항 연산자이며, 피연산자들의 결합 방향은 왼쪽에서 오른쪽이다.

    | 산술 <br>연산자 | 설명 |
    |:---:|:---|
    |+|왼쪽 피연산자의 값에 오른쪽 피연산자의 값을 더함.|
    |-|왼쪽 피연산자의 값에서 오른쪽 피연산자의 값을 뺌.|
    |*|왼쪽 피연산자의 값에 오른쪽 피연산자의 값을 곱함.|
    |/|왼쪽 피연산자의 값을 오른쪽 피연산자의 값으로 나눔.|
    |%|왼쪽 피연산자의 값을 오른쪽 피연산자의 값으로 나눈 후, 그 나머지를 반환함.|

    ```js
    var x = 10, y = 2;

    document.write(x + y); // 12

    document.write(x - y); // 8

    document.write(x * y); // 20

    document.write(x / y); // 5

    document.write(x % y); // 0
    ```

* **:two: 대입 연산자 & 복합 대입 연산자**

    > 대입 연산자는 변수에 값을 대입할 때 사용하는 이항 연산자이며, 피연산자들의 결합 방향은 오른쪽에서 왼쪽이다. 
    또한, 산술 연산자와 결합한 다양한 복합 대입 연산자가 존재한다.

    | 대입 <br>연산자 | 설명 |
    |:---:|:---|
    |=|왼쪽 피연산자에 오른쪽 피연산자의 값을 대입함.|
    |+=|왼쪽 피연산자의 값에 오른쪽 피연산자의 값을 더한 후, 그 결괏값을 왼쪽 피연산자에 대입함.|
    |-=|왼쪽 피연산자의 값에서 오른쪽 피연산자의 값을 뺀 후, 그 결괏값을 왼쪽 피연산자에 대입함.|
    |*=|왼쪽 피연산자의 값에 오른쪽 피연산자의 값을 곱한 후, 그 결괏값을 왼쪽 피연산자에 대입함.|
    |/=|왼쪽 피연산자의 값을 오른쪽 피연산자의 값으로 나눈 후, 그 결괏값을 왼쪽 피연산자에 대입함.|
    |%=|왼쪽 피연산자의 값을 오른쪽 피연산자의 값으로 나눈 후, 그 나머지를 왼쪽 피연산자에 대입함.|

    ```js
    'A = B'는 'A = B' 이다.
    'A += B'는 'A = A + B' 이다.
    'A -= B'는 'A = A - B' 이다.
    'A *= B'는 'A = A * B' 이다.
    'A /= B'는 'A = A / B' 이다.
    'A %= B'는 'A = A % B' 이다.
    ```

* **:three: 비교 연산자**
    
    > 비교 연산자는 피연산자 사이의 상대적인 크기를 판단하여,   
    **참(true)** 과 **거짓(false)** 즉 **Boolean**을 반환한다.   
    비교 연산자는 모두 두 개의 피연산자를 가지는 이항 연산자이며, 피연산자들의 결합 방향은 왼쪽에서 오른쪽이다.

    | 비교 <br>연산자 | 설명 |
    |:---:|:---|
    |==|왼쪽 피연산자와 오른쪽 피연산자의 값이 같으면 참을 반환함.|
    |===|왼쪽 피연산자와 오른쪽 피연산자의 값이 같고, 같은 타입이면 참을 반환함.|
    |!=|왼쪽 피연산자와 오른쪽 피연산자의 값이 같지 않으면 참을 반환함.|
    |!==|왼쪽 피연산자와 오른쪽 피연산자의 값이 같지 않거나, 타입이 다르면 참을 반환함.|
    |>|왼쪽 피연산자의 값이 오른쪽 피연산자의 값보다 크면 참을 반환함.|
    |>=|왼쪽 피연산자의 값이 오른쪽 피연산자의 값보다 크거나 같으면 참을 반환함.|
    |<|왼쪽 피연산자의 값이 오른쪽 피연산자의 값보다 작으면 참을 반환함.|
    |<=|왼쪽 피연산자의 값이 오른쪽 피연산자의 값보다 작거나 같으면 참을 반환함.|

    * 피연산자가 둘 다 숫자면, 해당 숫자를 서로 비교한다.

    * 피연산자가 둘 다 문자열이면, 문자열의 첫 번째 문자부터 알파벳 순서대로 비교한다.

    ```js
    var x = 3, y = 5;

    var a = "abc", b = "bcd";

    document.write((x > y));
    // y의 값이 x의 값보다 크므로 false

    document.write((a <= b));
    // 알파벳 순서상 'a'가 'b'보다 먼저 나오므로 'a'가 'b'보다 작음.

    document.write(x < a);
    // x의 값은 숫자이고 a의 값은 문자열이므로 비교할 수 없음.
    ```

* **:four: 논리 연산자**
    >논리 연산자는 주어진 논리식을 판단하여, 참(true)과 거짓(false)을 반환한다.   
    **&& 연산자**와 **|| 연산자**는 두 개의 피연산자를 가지는 이항 연산자이며, 피연산자들의 결합 방향은 왼쪽에서 오른쪽이다.   
    **! 연산자**는 피연산자가 단 하나뿐인 단항 연산자이며, 피연산자의 결합 방향은 오른쪽에서 왼쪽이다.

    | 논리 <br>연산자 | 설명 |
    |:---:|:---|
    |&&|논리식이 모두 참이면 참을 반환함. (논리 AND 연산)|
    |ll|논리식 중에서 하나라도 참이면 참을 반환함. (논리 OR 연산)|
    |!|논리식의 결과가 참이면 거짓을, 거짓이면 참을 반환함. (논리 NOT 연산)|

    ```js
    var x = true, y = false;

    document.write((x && y));
    // false (논리 AND 연산)

    document.write((x || y));
    // true  (논리 OR 연산)

    document.write(!x); 
    // false (논리 NOT 연산)
    ```
***

## 선택자 정리

* **:one: querySelector()**
    > 선택자로 찾은 여러개의 element 중 첫번째 element를 리턴한다.

    ```js
    태그 선택
    document.querySelector("div");

    Id 선택
    document.querySelector("#id");

    Class 선택
    document.querySelector(".class");
    ```

* **:two: querySelectorAll()**
    > 선택자로 찾은 여러개의 element를 모두 리턴한다.

    ```js
    태그 선택
    document.querySelectorAll("div");

    Id 선택
    document.querySelectorAll("#id");

    Class 선택
    document.querySelectorAll(".class");

* **:three: getElementById()**

    >ID 요소 선택

    ```js
    document.getElementById('test');
    ```
    * id는 유일한 값이므로, 하나의 element만 리턴한다.

* **:four: getElementsByClassName()**

    >Class 요소 선택

    ```js
    document.getElementsByClassName('test');
    ```
    * 클래스 이름을 가지는 모든 element 목록을 리턴한다.
    
    ```js
    document.getElementsByClassName('test1 test2');
    ```
    * 클래스 이름에 'test1'와 'test2' 모두를 포함하는 element만 리턴한다.

* **:five: getElementByTagName()**

    >태그 요소 선택

    ```js
    document.getElementByTagName('div');
    ```
    * 'div' 태그를 가지는 모든 element 목록을 리턴한다.

:link:[JS-Selector][javascript-study_03] : 자바스크립트 선택자 예시

[javascript-study_03]: https://lbsafe.github.io/JavaScript-study/javascript_study/html/study_03.html "JS-Selector"
***

## 리팩토링(Refactoring)

> 비효율적인 코드, 중복 된 코드를 정리하여 코드의 효율과 가독성을 높히면서 유지보수를 편리하게 만드는 개선 작업을 뜻한다.

*ex)* **AS-IS**
```js
<input id="night_day" type="button" value="toggle night" onclick="
    if(document.querySelector('#night_day').value === 'toggle night'){
        document.querySelector('body').style.backgroundColor = 'black';
        document.querySelector('body').style.color = 'white';
        document.querySelectorAll('a').forEach(function(item) {
            item.style.color = 'white';
        });
        document.querySelector('#night_day').value = 'toggle day'
    }else{
        document.querySelector('body').style.backgroundColor = 'white';
        document.querySelector('body').style.color = 'black';
        document.querySelectorAll('a').forEach(function(item) {
            item.style.color = 'black';
        });
        document.querySelector('#night_day').value = 'toggle night'
    }
">
```
*ex)* **TO-BE**
```js
<input id="night_day" type="button" value="toggle night" onclick="
    let target =  document.querySelector('body');
    let target_link =  document.querySelectorAll('a');
        
    if(this.value === 'toggle night'){
        target.style.backgroundColor = 'black';
        target.style.color = 'white';
        target_link.forEach(function(item) {
            item.style.color = 'white';
        });
        this.value = 'toggle day'
    }else{
        target.style.backgroundColor = 'white';
        target.style.color = 'black';
        target_link.forEach(function(item) {
            item.style.color = 'black';
        });
        this.value = 'toggle night'
    }
">
```

> 반복 되는 선택자를 변수로 선언하여 중복 된 소스를 정리하고, 코드의 유지보수와 성능을 높인다.

:link:[JS-Refactoring][javascript-study_05] : 자바스크립트 리팩토링 예시

[javascript-study_05]: https://lbsafe.github.io/JavaScript-study/javascript_study/html/study_05.html "JS-Refactoring"
***

## 배열(Array)

> 연관된 데이터를 모아서 관리하기 위해서 사용되는 데이터 타입.   
변수가 하나의 데이터를 저장하기 위한 것이라면 배열은 여러 개의 데이터를 저장하기 위한 것이다.

1. 배열 추가

    * Array.push();

        > 배열의 끝에 요소 추가

        ```js
        let array = ["oh", "hello"];

        document.write(array[0]); // oh
        document.write(array[1]); // hello

        /* 배열 요소 추가 */
        array.push("world");

        document.write(array);
        -> oh, hello, world
        ```

    * Array.unshift();

        > 배열의 앞쪽에 요소 추가

        ```js
        let array = ["oh", "hello"];

        document.write(array[0]); // oh
        document.write(array[1]); // hello

        /* 배열 요소 추가 */
        array.unshift("world");

        document.write(array);
        -> world, oh, hello 
        ```

    * Array.splice();

        > 지정 index 위치에 요소 추가

        ```js
        let array = ["oh", "hello"];

        document.write(array[0]); // oh
        document.write(array[1]); // hello

        /* 배열 요소 추가 */
        array.splice(2, 0, "keonhee");
        index 2번 요소 위치 뒤에 요소 추가

        document.write("array : " + array);
        -> oh, hello, keonhee

        -------------------------------------

        let array = ["oh", "hello", "keonhee"];

        document.write(array[0]); // oh
        document.write(array[1]); // hello
        document.write(array[2]); // keonhee

        array.splice(1, 0, "BeeMo", "lbsafe");
        index 1번 요소 위치 뒤에 2개의 요소 추가

        document.write("array : " + array);
        -> oh, BeeMo, lbsafe, hello, keonhee
        ```

2. 배열 삭제
   * Array.pop();

        > 배열의 끝에 요소 삭제

        ```js
        let array = ["oh", "hello", "keonhee"];

        document.write(array[0]); // oh
        document.write(array[1]); // hello
        document.write(array[2]); // keonhee

        /* 배열 요소 삭제 */
        array.pop();

        document.write(array);
        -> oh, hello
        ```

   * Array.shift();

        > 배열의 앞쪽에 요소 삭제

        ```js
        let array = ["oh", "hello", "keonhee"];

        document.write(array[0]); // oh
        document.write(array[1]); // hello
        document.write(array[2]); // keonhee

        /* 배열 요소 삭제 */
        array.shift();

        document.write(array);
        -> hello, keonhee
        ```

    * Array.splice();

        > 지정 index 위치에 요소 삭제

        ```js
        let array = ["oh", "hello", "keonhee"];

        document.write(array[0]); // oh
        document.write(array[1]); // hello
        document.write(array[2]); // keonhee

        /* 배열 요소 추가 */
        array.splice(2, 1);
        index 2번 요소 위치부터 1개의 요소 삭제

        document.write("array : " + array);
        -> oh, hello

        /* 제거한 요소를 반환 받을 수 있음 */
        removed = array.splice(2, 1);
        -> removed = 'keonhee'

        -------------------------------------

        let array = ["oh", "hello", "keonhee"];

        document.write(array[0]); // oh
        document.write(array[1]); // hello
        document.write(array[2]); // keonhee

        array.splice(1, 2);
        index 1번 요소 위치부터 2개의 요소 삭제

        document.write("array : " + array);
        -> oh
        ```


   * delete 연산자

        > delete로 배열을 삭제할 경우 요소는 그대로 존재하며 값만 삭제   
        삭제가 아닌 값을 빈 값으로 변경하기 때문에 삭제보다는 변경에 가까운 개념이다.

        ```js
        var array = ['a', 'b', 'c', 'e', 'f'];

        delete array[1];

        -> array = ["a", undefined, "c", "e", "f"]
        ```
3. 함수를 사용하지 않고 추가, 삭제 방법​​
    > 자바스크립트는 배열의 길이를 동적으로 변경할 수 있다

    ```js
    var array = ['a', 'b', 'c'];

    array[array.length] = 'e'; // 배열의 끝에 요소를 추가 
    -> array = ['a', 'b', 'c', 'e'];

    array.length = array.length - 1; // 배열의 크기를 하나 줄인다
    -> array = ['a', 'b', 'c']

    array[5] = 'g'; // index 5 에 요소를 추가, 빈요소([3],[4])는 undefined
    array = ["a", "b", "c", undefined, undefined, "g"]
    ```

:warning:배열 중간의 요소를 추가 하거나, 삭제할 경우 함수를 사용하는 것이 편리하다.

:link:[JS-Array][javascript-study_06] : 배열 개념 연습 예시

[javascript-study_06]: https://lbsafe.github.io/JavaScript-study/javascript_study/html/study_06.html "JS-Array"
***