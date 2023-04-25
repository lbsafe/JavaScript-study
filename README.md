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
    * 미정의된(초기화 되지 않은, 기본초기값), 들어오지 않은 자료형.

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

    * 아무것도 참조하지 않은 자료형. (객체를 담기위한 변수를 초기화 하는 상태)

    ```js
    ex :
    var data = null;
    ``` 

* :heavy_exclamation_mark: 이 외 **함수(function)**, **객체(object)** 등이 존재한다.
***