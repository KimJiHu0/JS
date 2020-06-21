# 작성방식 3가지

>  JavaScript 작성방식은 3가지가 있다.
>
> - **inline방식 :** onclick이벤트 내에서 바로 작성을 하는 것이다.
> - **내부 작성 방식 :** onclick이벤트에 함수를 넣어주고 html내에서 함수를 만들어주는 것이다.
> - **외부 작성 방식 :** html내에서가 아닌 다른 파일을 만들어 작성하고 불러오는 것이다.
>
>  
>
> **인라인방식**
>
> ```html
> //body태그 안에 작성
> <ol>
>     <li onclick="alert("inline방식으로 실행됌!")">inline방식</li>
> </ol>
> ```
>
> inline방식으로 작성한 html이다.
>
> 화면에는 inline방식 이라는 문구가 출력이 될 것이고 onclick이벤트를 작성해서 alert창을 
>
> 괄호 안에 문구가 뜨게 했다.
>
> **alert() :** 웹페이지에서 보이는 확인버튼밖에 없는 경고창
>
> --------
>
>  
>
> **내부작성방식**
>
>  ```javascript
> function embededTest(){
> 	var doc = document.getElementsByTagName("li")[1];
>     doc.style.color = "red";
>     doc.innerHTML = "<strong>글자가 바뀌었습니다!!</strong>";
> }
>  ```
>
> ```html
> //body안에 작성
> <ol>
>     <li onclick="alert("inline방식으로 실행됌!")">inline방식</li>
>     <li onclick="embededTest();">내부 작성 방식</li>
> </ol>
> ```
>
> "내부 작성 방식" 이라는 문구를 클릭하게 되면 embededTest함수가 실행되게 된다.
>
> 같은 html내에서 작성된 js이다.
>
> doc라는 변수에 li태그들 중에 1번지 인덱스에 위치한 li태그를 담았다.
>
> 그리고 doc의 color을 red로 바꾸었고, doc의 문구를 innerHTML로 인해 문구를 바꾸었다.
>
> ---------
>
>   
>
> **외부작성방식**
>
> ```javascript
> function test(){
>     window.alert("외부 작성 방식");
> }
> window.onload=function(){
>     alert("윈도우 로딩 후 !!");
> }
> ```
>
> html 내부가 아닌 다른 곳에 basic.js라는 파일로 js를 작성하였다.
>
> 위에서 작성한 **window**라는 뜻은 생략이 가능하다.
>
> **window.onload=function(){}**은 페이지가 로딩이 된 후에 바로 실행되는 의미다.
>
> 그래서 새로고침을 하거나 창을 새로 띄운다면 **윈도우 로딩 후!!** 라는 경고창이 가장 먼저 뜰 것이다.
>
> 이 파일을 가져와서 사용해야한다.
>
> ```html
>  	<script type="text/javascript" src="resources/js/basic.js">
>  	
>  	//이 사이에 작성하면 안됌
>  	
>  	</script>
> ```
>
> 외부의 파일을 가져오려면 위의 구문처럼 작성을 해줘야 사용할 수 있다.
>
>  ```html
> 	<ol>
> 		<li onclick="test();">외부 작성 방식 (*.js파일)</li>
> 	</ol>
>  ```
>
> 
>
> -----
>
> # 변수
>
>  **변수의 선언 규칙**
>
> - 대소문자를 구분한다.
> - 영문, _, $로 시작할 수 있다.
> - 영문, _, $, 숫자를 포함할 수 있다.
> - 키워드나 예약어를 사용할 수 없다.
>
>   
>
> **변수의 범위**
>
> - 전역변수 : window객체에 포함되는 변수이다. 다른 함수들에서 공용으로 사용할 수 있고 값이 유지된다.
> - 지역변수 : 함수나 객체 내부에 선언되고 실행이 종료되면 사라진다.
>
>   
>
> ```javascript
> //전역변수
> var variable01 = 10;
> 
> function test01(){
>     //java에서 sum+=1 과 같은 의미이다.
>     variable01 = variable01 + 5; 
>     document.getElementById("v01").innerHTML = "<b style='color : red; background : yellow;'>" + variable01 + "</b>";
> }
> 
> function test02(){
>     var varibale02 = variaable01 + 100;
>     document.getElementById("v02").innerHTML = "<b style='color : red; background : yellow;'>" + variable02 + "</b>";
> }
> ```
>
> ```html
> <dt>변수의 범위</dt>
> <dd>
> 1.전역변수 : window 객체에 포함되는 변수. 다른 함수들에서 공용으로 사용할 수 있다.(값이 유지)
> <button onclick="test01();">확인</button>
> </dd>
> <dd id="v01"></dd>
> 		
> <dd>
> 2.지역변수 : 함수나 객체 내부에 선언되고 실행이 종료되면 사라짐
> <button onclick="test02();">확인</button>
> </dd>
> <dd id="v02"></dd>
> ```
>
> ![](https://postfiles.pstatic.net/MjAyMDA2MTFfMjQ5/MDAxNTkxODY5Nzk0MTgw.uqNUzDhhYN5uRUbb_uNukG7CD17dkwGaSFBUW1ot7yEg.tYM70fYqG5fad-SRnc538ZyEaGU_8Q7frm7DFGsbNDwg.PNG.rgusqls/image.png?type=w773)
>
>  여기서 다시 전역변수 확인버튼을 누르게 되면 30이라는 값이 유지 된 채 +가 된다.
>
> 지역변수 확인버튼을 누르게되면 전역변수 값에서 +100을 하게 된다.
>
> --------
>
> # 변수 선언 및 저장
>
>  var 키워드를 사용하여 변수를 선언한다.
>
> 변수의 타입은 저장되는 타입에 따라 결정된다.
>
> ```javascript
> function test03() {
> 		//String type 문자열
> 		var variable03 = "문자";
> 		alert(variable03 + "의 타입 : " + typeof(variable03));
> 		
> 		//숫자
> 		variable03 = 5;
> 		alert(variable03 + "의 타입 : " + typeof(variable03));
> 		
> 		//논리
> 		variable03 = null;
> 		alert(variable03 + "의 타입 : " + typeof(variable03));
> 		
> 		//array (Object)
> 		variable03 = [1,3,5,7,9];
> 		alert(variable03 + "의 타입 : " + typeof(variable03));
> 	}
> ```
>
> 문자의 타입은 String,
>
> 숫자의 타입은 Number
>
> 논리의 타입은 object
>
> 배열의 타입은 object
>
> **var**이라는 변수 선언에는 모든 타입을 담을 수 있다.
>
>  
>
>  **타입의 종류**
>
>  문자 String
>
> 숫자 Number
>
> 논리 Boolean
>
> null
>
> 객체 object
>
> 함수 function

