# Number

>  Number은 javascript에서 기본적으로 제공하는 객체중 하나이다.
>
> Number객체는 정수, 실수를 전부 다루는 객체이다.
>
> #### [ 속성 ]
>
> **NaN** : 숫자가 아닌 값
>
> **infinity** : 범위를 벗어난 값
>
> #### 그 밖의 예외속성
>
> **undefined** : 변수가 정의되지 않음.
>
> **null** : 변수는 있지만 값이 없다. 
>
>  
>
>  ```html
> <button onclick="numberObj();"> number객체</button>
> <button onclick="isNum();"> 숫자 판별</button>
> 
> <p id="inputTxt"></p>
>  ```
>
> ```javascript
> function numberObj(){
>     var out = document.getElementById("inputTxt");
>     
>     //기본 선언
>     //타입 변수 = 값;
>     var num = 10;
>     //객체생성
>     var num2 = new Number(7);
>     
>     out.innerHTML= num+"<br/>";
>     out.innerHTML += num2 + "</br>";
>     
>     //NaN : 숫자판별
>     //parseInt안의 값이 숫자면 true, 아니면 false
>     out.innerHTML += "NaN 속성 : " + parseInt("a") + "</br>";
>     
>     
>     //3. infinity ( 표현 가능한 값보다 더 큰 수) or 더 작은 수
> 	out.innerHTML += "infinity 속성 : " + (Infinity/100) + "<br/>";
> 	out.innerHTML += "infinity 속성 : " + (Number.MAX_VALUE + 0.00001e+308)  + "		<br/>";
>     
>     //toFixed(); : 실수형의 소수점 자리수를 지정하고 문자열로 반환.
>     var number01 = 3333.3456;
>     out.innerHTML += "toFixed : " + number01.toFixed(2) + "</br>"";
>     //3333.3456의 소수점 2번째리수를 올림하고 이를 문자열로 반환한다.
>     
>     //toString(n); : n진수로 변환하여 문자열로 반환
>     var number02 = 123;
> 	out.innerHTML += "toString(16) : " + number02.toString(16);
> }
> 
> function isNum(){
>     var out = document.getElementById("inputTxt");
>     
>     var num = prompt("숫자만 입력하세요");
>     
>     //만일 숫자라면
>     if(!isNaN(num)){
>         out.innerHTML= num + "은 숫자입니다.";
>     } else {
>         out.innerHTML = num + "은 숫자가 아닙니다.";
>     }
> }
> ```
>
> 
>
> #  transObj
>
> ####  숫자형 형 변환 number() 함수
>
> 정수 or 실수의 문자형을 **숫자형**으로 변환.
>
> **숫자형은 정수와 실수를 모두 받을 수 있다.**
>
> html은 값이 모두 문자열,문자형이다. 그래서 이를 숫자형으로 변환해주는 것이다.
>
> ```javascript
> function numTest(val){
>     var vals = Number(val) + 5;
>     alert(vals + " : " + typeof(vals));
> }
> ```
>
> ```html
> <input type="text" id="num"/>
> <button onclick="numTest(num.value);">확인</button>
> ```
>
> input태그에 입력해서 넣어준 값은 문자형 혹은 문자열이다.
>
> 값을 넣어주고 확인버튼을 누르면 numTest이라는 함수가 실행되는데 그 안에 파라미터로 num의 value
>
> 즉, 사용자가 입력한 값이 들어가게 된다.
>
> 그럼 함수 numTest안의 파라미터로 입력한 값이 val이라는 이름으로 들어가게 된다.
>
> Number()은 문자열을 숫자형으로 바꿔준다. 그리고 입력한 값에서 5를 더해서 화면에 출력해주고
>
> type은 Number 으로 출력하게 된다.
>
>  
>
>  
>
> ####  정수형 형 변환. parseInt()함수
>
>  정수 or 실수의 문자형을 **정수**로 반환
>
> parseInt()는 정수 혹은 실수의 문자형을 정수로만 반환한다.
>
> ```javascript
> function intTest(val){
>     var vals = parseInt(val) + 5;
>     alert(vals + " : " + typeof(vals));
> }
> ```
>
> ```html
> <input type="text" id="int"/>
> <button onclick="intTest(int.value);">확인</button>
> ```
>
> 사용자가 text에 값을 입력하고 확인을 누르게 되면 intTest함수가 실행된다.
>
> 사용자가 입력한 값은 intTest파라미터로 들어간다.
>
> 그럼 js에서 함수 val에 그 값이 들어오는데 이 값을 parseInt(val)을 해주면 문자열로 받은 값을
>
> 정수형으로 변환해주고 5를 더해준다.  이 값의 타입은 Number타입이다.
>
>  
>
> ####   실수형 형 변환 parseFloat()
>
>  실수형태 문자형을 숫자형으로 반환하는데 실수만 가능하다.
>
> ```javascript
> function floatTest(val){
> 
> 	var vals = parseFloat(val) + 5;
> 	alert(vals + " : " + typeof(vals);
> }
> ```
>
> ```html
> <input type="text" id="float"/>
> <button onclick="floatTest(float.value)">확인</button>
> ```
>
> 사용자가 텍스트에 값을 입력하고 확인을 누르면 입력한 값이 파라미터로 들어온다.
>
> 그리고 함수가 실행되면서 입력한 값이 문자열이었는데 그 값을 실수형으로 변환한다.
>
> 그 타입은 Number이다.
>
>  
>
> ####  검증함수 / 문자열로 된 식을 계산
>
>  ```javascript
> function evalTest(){
>     var val = document.getElementsByName("evalue")[0];
>     
>     if(confirm("작성하신 코드가 맞습니까? ->" + val.value)){
>         document.getElementsByTagName("span")[0].innerHTML = "<b>계산결과 : " + 
>             eval(val.value) + "</b>" >;
>     } else {
>         val.value = "5+10";
>     }
> }
>  ```
>
>  ```html
> <input type="text" name="evalue" placeholder="예) 5+10"/>
> <button onclick="evalTest()">계산</button>
> <span></span>
>  ```
>
> 텍스트에 입력하고 버튼을 클릭하면 evalTest함수가 실행된다.
>
> val이라는 변수에 name이 evalue의 0번지에 있는 태그를 담는다.
>
> 만약에 작성하신코드 : evalue0번의 value(사용자가 입력한값)가 맞다면
>
> span태그의 0번지 html을 계산결과 :  eval()해준다.
>
> **eval() : 계산을 해주는 기능**
>
> **confirm() : 확인과 취소버튼을 제공하고 확인버튼을 누르면 true, 취소버튼을 누르면 false**