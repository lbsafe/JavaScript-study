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

### 데이터 타입

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

> 대입 연산자는 변수에 값을 대입할 때 사용하는 이항 연산자이며, 피연산자들의 결합 방향은 오른쪽에서 왼쪽이다. 
또한, 산술 연산자와 결합한 다양한 복합 대입 연산자가 존재한다.

* **:one: 산술 연산자**

    | 산술 연산자 | 설명 |
    |:---:|:---|
    |+|왼쪽 피연산자의 값에 오른쪽 피연산자의 값을 더함.|
    |-|왼쪽 피연산자의 값에서 오른쪽 피연산자의 값을 뺌.|
    |*|왼쪽 피연산자의 값에 오른쪽 피연산자의 값을 곱함.|
    |/|왼쪽 피연산자의 값을 오른쪽 피연산자의 값으로 나눔.|
    |%|왼쪽 피연산자의 값을 오른쪽 피연산자의 값으로 나눈 후, 그 나머지를 반환함.|

* **:two: 대입 연산자 & 복합 대입 연산자**

    | 대입 연산자 | 설명 |
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
***