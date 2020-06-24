# DOM 탐색

>  **Docement OBbject Model** 이라고 한다.
>
> **HTML이나 XML같은 문서의 태그들을 조작 가능하도록 객체화** 시킨 것이다.
>
> jQuery는 CSS에서 사용하던 **Selector 표현방식**으로 DOM요소를 쉽고 간결하게 접근할 수 있도록 하고
>
> 세밀하게 DOM접근을 할 수 있도록 고급 필터 또한 제공한다.
>
> 
>
> **ID선택자 :** 태그에서 주어진 속성 중 id로 찾는다. id는 고유한 속성이기 때문에 겹칠 수 없다.
>
> ```javascript
> function searchId(){
>     var doc = document.getElementById("test01");
>     doc.innerHTML = "id로 탐색 완료";
> }
> //태그 id가 test01인 것을 doc에 담아준 것.
> ```
>
> **NAME선택자 :** 태그에서 주어진 속성 중 name으로 찾는다.
>
> ```javascript
> function searchName(){
>     var doc = document.getElementsByName("test02");
>     doc[1].innerHTML="Name으로 탐색 완료";
> }
> //태그의 name이 test02인 것을 doc에 담아준 것
> ```
>
> **TAGNAME선택자 :** 태그에서 주어진 속성 중 태그이름으로 찾는다.
>
> ```javascript
> function searchTagName(){
>     var doc = document.getElementsByTagName("p");
>     doc[1].innerHTML="TagName으로 탐색 완료";
> }
> //태그이름이 p태그인 애를 찾아서 doc에 넣어준 것.
> ```
>
> **CLASS선택자 :** 태그중에서 주어진 속성 중 클래스이름으로 찾는다.
>
> ```javascript
> function searchClass(){
> 	var doc = document.getElementsByClass("test03");
>     doc[1].innerHTML="Class로 탐색 완료";
> }
> //태그의 class명이 test03인 것을 doc에 넣으준 것
> ```
>
> **CSS선택자 :** querySelectorAll() 을 통해서 #은 id, .은 class .. 로 찾는다.
>
> id를 제외한 나머지 선택자들은 html 안에 몇개의 태그들이 있을지 모르기 때문에 NODELIST형식으로 불러온다.그렇게 때문에 찾아온 태그가 그 태그들 중 몇번지에 위치하고 있는지 명시해주어야한다.
>
> ```javascript
> function searchQS(){
>     var doc = document.querySelectorAll("#test04");
>     doc[1].innerHTML="CSS선택자로 탐색 완료";
> }
> //#이라는 것은 id를 찾아올 때 사용하는 특수문자인데, css선택자로 찾아올 수 있게 명령어를 썼기 때문에 사용할 수 있다.
> ```
>
> 
>
> #  Object
>
>  자바스크립트는 객체기반의 스크립트 언어이다.
>
> 객체란 **여러 속성을 하나의 변수에 저장할 수 있도록 해주는 데이터 타입**으로 key와 value를
>
> 저장할 수 있는 구조이다. 객체는 변수이지만 많은 값을 저장할 수 있다.
>
>  
>
>  **[ 객체의 종류 ]**
>
> - 배열
> - 함수
> - 객체
> - 날짜
> - 수학
> - 정규표현식
> - boolean
> - 숫자
> - 문자열
>
>   
>
> **[ 객체의 구성 ]**
>
> **메서드** : 기능 정의
>
> **속성** : 객체 내부 데이터
>
> **this** : 객체 내부의 메서드나 속성을 정의할 때 사용
>
> **프로토타입** : 객체의 확장
>
>  
>
> ```html
> <button onclick="objTest();">클릭!</button>
> ```
>
>  ```javascript
> function myQclass(){
>     this.name = "kh정보교육원";
>     var name2 = "빅데이터 전문가 과정";
>     this.getName2 = function(){
>         return name2;
>     }
> }
> 
> myQclass.prototype.printSubjects = function(){
>     alert(this.name + this.Name2() + " : java, db, ui");
> }
> 
> function objectTest(){
>     var cls = new myQclass();
>     
>     cls.printSubjects();
> }
>  ```
>
> 위의 경우 버튼을 클릭하게 되면 objectTest()라는 함수가 실행된다.
>
> 이 함수에는 cls변수에 myQclass라는게 있다. 이클립스는 이를 먼저 찾아준다.
>
> myQclass에 this. 란 내가 선택한, myQclass 자기자신의 name을 kh정보교육원이라고 지정했고
>
> name2는 빅데이터 전문가 과정 이라고 지정했다.
>
> ]내가 선택한 것의 getNname2라는 변수에 함수를 넣고 return name2를 했다.
>
> myQclass.prototype.printSubjects는 myQclass에 printSubjects라는 기능을 추가해준것이다.
>
> 그리고 함수를 실행해서 이것의  name과 리탄한 name를 문자열과 합쳐서 출력한다.
>
>  
>
>   
>
>  
>
>  
>
>  
>
>  
>
>  
>
>  
>
>  
>
>  
>
>  
>
>  
>
> 