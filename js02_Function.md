# Function

>  window 객체에서 제공하는 대화형 함수의 종류에는 3가지가 있다.
>
> - **alert() :** 단순한 대화창이며 경고, 코드, 디버깅, 단순출력
> - **confirm() :** 확인, 취소버튼이 제공(true/false)
> - **prompt() :** 텍스트박스 제공, 확인/취소버튼 제공. 확인->텍스트창 / 취소->null
>
> 
>
>  ```javascript
> function alertTest(){
>     alert("단순 대화창(내용 출력)");
> }
>  ```
>
> ![](https://postfiles.pstatic.net/MjAyMDA2MjNfMjU0/MDAxNTkyODcxMTc3OTM5.ht00wLld-AhWNohdgSr3sDXFA5fSmlo7lg4NCtJq9qQg.uXCnh2o4PnkXjMoUMW5B9jrHb-fgqDSFr2uY7pvR08sg.PNG.rgusqls/image.png?type=w773)
>
>  
>
>  확인버튼만 제공되는 경고창이 뜬다.
>
>  
>
> ```javascript
> function confirmTest(){
>     if(confirm("배경을 파란색으로 변경할까요?")){
>         document.body.style.backgroundColor = "skyblue";
>     } else {
>         document.body.style.backgroundColor = "white";
>     }
> }
> ```
>
>  ![](https://postfiles.pstatic.net/MjAyMDA2MjNfMzkg/MDAxNTkyODcxMTk2Njc4.siosgeScwZEiQ5rAp9as4GXKmWKyo88DpAy2eBMgMX8g.EzqwIiPUnDSziofLRptAluIczykGyBMpj1uYLvScNBQg.PNG.rgusqls/image.png?type=w773)
>
> 
>
> confirm은 확인/취소버튼 두가지가 제공된다.
>
> 배경을 파란색으로 변환할까요라는 문구가 뜨는데 확인버튼을 누르면 if문이 참이되어
>
> body의 배경을 변환하고, 취소를 누르면 body의 배경을 흰색으로 변환한다.
>
>  
>
>  ```javascript
> function promptTest(){
>     var txt = propmt("좋아하는 과목을 선택해주세요\n [1.자바 2.db 3.web]");
>     
>     switch(txt){
>         case "1" :
>             alert("역시 자바");
>             break;
>         case "2" :
>             alert("db 좋죠");
>             break;
>         case "3" :
>             alert("홈페이지 만들기 재밌죠");
>             break;
>         case null :
>             alert("취소하면 다 싫은건가요?");
>             break;
>         default :
>             alert("1,2,3번 중 하나만 선택해주세요");
>             break;
>     }
> }
>  ```
>
> ![](https://postfiles.pstatic.net/MjAyMDA2MjNfMTQ4/MDAxNTkyODcxMjIyMDcx.37dnv8FiC6qjyimIwB3Jf2oBirufkYjzf1WshM1Mtd0g.82gaae5krGep9pmdclULuhKN1Obz2wtaNOvdHenMbPwg.PNG.rgusqls/image.png?type=w773)
>
>  위와 같이 prompt는 텍스트를 입력할 수 있게 텍스트칸이 제공되며 확인버튼과 취소버튼이
>
> 제공된다. 위에서는 내가 텍스트로 입력한 값을 txt라는 변수에 담았다.
>
> 그 담은 txt값을 switch의 값으로 넣었다. 만일 내가 1을 입력하면 case "1"에 해당하는 alert창,
>
> 2를 입력하면 case "2"에 해당하는 alert창이 뜬다.
>
> 하지만 입력한 값이 null값이면 ""취소하면 다 싫은건가요?" 라는 문구가 뜨고,
>
> 취소버튼을 누르게 되면 "1,2,3번중 하나만 선택해주세요"라는 문구가 뜬다.
>
>  
>
> ###  함수의 종류
>
> - **명시적함수 :** JS에서 일반적으로 사용되는 함수의 모양이다.
>
> ```javascript
> function func01(){
>     //실행문 작성!
> }
> ```
>
> - **익명함수 :** JS는 함수를 변수에 담을 수 있다. 함수를 변수에 담아서 이벤트에서 ()로 실행한다.
>
> ```javascript
> var func02 = function(){
>     //실행문 작성!
> }
> ```
>
> - **리터럴함수 :** 파라미터 하나 받아서 호출해주는 함수
>
> ```javascript
> function myLiteralPrn(literal){
>     literal("안녕하세요 함수입니다.");
> }
> 
> function func03(){
>     myLiteralPrn(function(msg){
>         alert(msg);
>     });
> }
> ```
>
> 이렇게 되면 "안녕하세요 함수입니다."가 출력이 된다.
>
> onclick이벤트를 클릭했을 때 func03이라는 함수가 실행된다. myLiteralPrn이라는 함수를 먼저 찾게 되는데
>
> 위에서 보면 literal이라는 것을 파라미터로 받고 있다.
>
> myLiteralPrn(function(msg){alert(msg);}); = myLiteralPrn(literal){}과 같은 구조이다.
>
> function(msg){alert(msg);} - literal이라고 할 수 있다.
>
> literal뒤에()를 붙여주면 이러한 함수를 실행해달라는 의미이다.
>
> function(msg){alert(msg);}("안녕하세요 함수입니다."); 이렇게 된 것이다.
>
> 그리고 "안녕하세요 함수입니다."를 msg로 전달이 된 것이다.
>
>  
>
> - **클로저함수 :** 외부함수 안에 있는 내부함수를 의미.(외부함수에서 접근가능 = 변수, 파라미터)
>
> ```javascript
> function closureTest(val){
>     var msg =  "!!!!!";
>     
>     function addVal(){
>         alert(val + msg);
>     }
>     return addVal;
> }
> var amEud = closureTest("자바스크립트");
> 
> function pmEdu(val){
>     closureTest(val)();
> }
> 
> 
> <label for="am">오전강의</label>
> <input type="text" value="클릭" onclick="amEdu();" />
> 
> <label for="pm">오후강의</label>
> <input type="text" id="pm" />
> <input type="button" value="클릭" onclick="pmEdu(pm.value);" />
> ```
>
> amEdu를 클릭하게 되면 closureTest라는 함수가 실행되며 파라티머토 "자바스크립트"라는 값이
>
> 들어가게 된다. 그럼 closureTest라는 함수의 val이 "자바스크립트"가 되고, 클로저함수인 addVal이
>
> 실행되어 val("자바스크립트") + msg("!!!!!")를 더해줘서 alert창으로 띄운다.
>
> 이러한 함수를 return한다.
>
>   
>
>  오후강의를 클릭하게 되면 pmEdu라는 함수가 실행된다. 파라미터로 pm.value를 받게 되는데
>
> 내가 입력한 값을 의미한다. pmEdu의 val은 내가 입력한 값이 되는 것이다.
>
> closureTest()안에 val을 (내가 입력한 값) 넣어줬기 때문에 내가 입력한값 + !!!!를 해서 출력이 된다.
>
>  
>
> ```javascript
> function valTest(){
> 	var val="";
> 	for(var i = 0; i < arguments.length; i++){
> 		val += arguments[i]+" ";
> 	}
> 	alert(val);
> }
> 
> <h2 onclick="valTest('kh', '정보', '교육원', 'Qclass');">args(arguments)</h2>
> ```
>
> `arguments` 객체는 모든 함수 내에서 이용 가능한 지역 변수입니다. `arguments` 객체를 사용하여 함수 내에서 모든 인수를 참조할 수 있으며, 호출할 때 제공한 인수 각각에 대한 항목을 갖고 있습니다. 항목의 인덱스는 0부터 시작합니다.