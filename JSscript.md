# JS script

## 선언문

* 내부 선언 방식
```js
<script>
   자바스크립트 코드
</script>
```

* 외부 선언 방식 ex) `<script src="자바스크립트 파일 경로"></script>`

* 변수 -> var 변수명 = 값;
* for, if, while, switch 모두 동일
* ex ) var num = prompt("숫자를 입력하세요","0");
* ex ) document.write(num + " 결과 입니다.");
* ex ) window.document.write(num);

## 객체

* 내장 객체 : 자바스크립트 엔진에 객체를 생성할 수 있는 함수가 내장되어, 필요한 경우에 생성하여 사용할 수 있다.
  ex) 참조 변수 = new 객체 생성 함수();

* 브라우저 객체 : 브라우저에 내장된 객체를 가리킨다.

## 함수

* 스코프 : 외부에서 내부 함수의 접근이 불가하다. 스코프 내의 영역에서만 호출 가능 
```JS
function outerFunction(){
   var 변수명;
   function innerFunction(){
     스크립트 코드;
   }
}
```

* 지역변수, 전역변수 

## 제이쿼리
-> 자바스크립트 라이브러리 언어이며, 자바스크립트의 호환성을 해결함. 애니메이션을 쉽게 구현할 수 있도록 개발되었다.

* 선택자 : HTML 요소를 선택하여 가져옵니다.
ex) 
```JS
$(function(){
   $("요소 선택").css("속성", "값");
})
```

```HTML
<script>
    $(function(){
        $(".wrap_1").css("border","1px solid orange");
        $(".wrap_1 p").eq(2).css("background-color","yellow");
        $(".active").next("p").css("background-color","aqua");
        $("input[type=text]").css({"background-color":"orange"});
        $(".wrap_1 p").eq(1).removeClass("active");
        $(".wrap_1").append("<p>텍스트2</p>");
    });
    </script>
<body>
    <div class="wrap_1">
        <p>텍스트1</p>
        <p class="active">내용2</p>
        <p><a href="#">네이버</a></p>
        <p>
            <input type="text" value="hello">
        </p>
    </div>
    
</body>
```

## 이벤트
-> 사이트에 방문자가 취하는 모든 동작

* 핸들러 : 이벤트가 발생했을 때 호출되는 함

* 단독이벤트 등록 : ex) $("#btn").click(function(){ 스크립트 코드 });
* 그룹이벤트 등록 : ex) $("#btn").on("이벤트 종류", function(){ 스크립트 코드 });
* 선택자, 이벤트 실습 
```HTML
<script>
    $(function(){
        // $(".btn1 a").mouseover(function(){
            // alert("hello");
        // })
        // $(".btn1 a").focus(function(){
            // alert("hello");
        // })
        $(".btn1 a").on("click", function(){
            var ts = $(this);
            //ts.css("background-color","yellow");
            $(".btn1").next("ul").filter(":visible").hide();
            ts.parent().next().show();
            return false;
        })
    });
</script>
<body>
    <p class="btn1"><a href="#">이벤트 대상 1</a></p>
    <ul style="display:none">
        <li>리스트1</li>
        <li>리스트2</li>
        <li>리스트3</li>
    </ul>
    <p class="btn1"><a href="#">이벤트 대상 2</a></p>
    <ul style="display:none">
        <li>리스트4</li>
        <li>리스트5</li>
        <li>리스트6</li>
    </ul>
    
</body>
```

## 애니메이션

* 효과 메서드 : 요소를 역동적으로 숨겼다 보이도록 해주는 매서드, 선택한 요소에 동작을 적용시킬 수 있다.
* 효과 메서 사용법 : ex) $(요소 선택).효과 메서드(효과 소요 시간, 가속도, 콜백함수)
* 애니메이션 사용법 : ex) $(요소 선택).animate({애니메이션에 적용할 속성과 값}, 가속도, 콜백함수);
* 실습 1

```HTML
<script>
    $(function(){
        $(".btn1").on("click", function(){
            var ts = $(this);
            if(ts.text() == "숨김"){
                $(".wrap").slideUp(1000, function(){
                $(".btn1").text("노출");
                });
            }
            else{
                $(".wrap").slideDown(1000, function(){
                $(".btn1").text("숨김");
                });
            }
            
        })
    });
</script>
<body>
    <p class="btnWrap">
        <button class="btn1">숨김</button>
    </p>
    <div class="wrap">
        <p class="txt1">내용1</p>
        <p class="txt1">내용2</p>
    </div>
</body>
```

* 실습 2

```HTML
<style>
        *{margin:0;padding:0;}
        body{
            padding:20px;
        }
        .btnWrap{margin-bottom: 10px;}
        .wrap{
            max-width: 600px;
            border : 1px solid #000;
        }
        .txt1{
            width: 10%;
            text-align: center;
            background-color: aqua;
        }
</style>
<script>
    $(function(){
        var txt1 = $(".txt1");
        var count = 1;

        $(".btnWrap button").on("click", function(){
            var ts = $(this);
            if(ts.hasClass("backBtn")){
                count--;
                if(count<1){
                    count = 1;
                    return;
                }
                txt1.stop(true,true).animate({marginLeft:"-=10%"},500);
            }
            else{
                count++;
                if(count>10){
                    count = 10;
                    return;
                }
                txt1.stop(true,true).animate({marginLeft:"+=10%"},500);
            }
            console.log(count);
        })

    });
</script>
<body>
    <p class="btnWrap">
        <button class="backBtn">Back</button>
        <button class="goBtn">Go</button>
    </p>
    <div class="wrap">
        <p class="txt1">내용1</p>
    </div>
</body>

```
## 제이쿼리 비동기 방식 연동 

* Ajax : Asychronouse Javascript and Xml로 비동기 방식으로 데이터를 전송하고, 요청하는 방식이다.
* 동기식 : Client Computer -> (request) ->  Server Computer -> (response) ->  Client Computer
* 비동기식 : Client Computer -> (request) (response) <- Server Computer

* Ajax 기본형
ex) 
```HTML
$.ajax({
	url : "전송 페이지(action url)",
	type : "전송 방식(get,post)",
	data : "전송 데이터",
	dataType : "요청한 데이터 타입(json, html, xml, text)",
	success : function(data){
		전송 선공하면 실행될 코드;
		},
	error : function(){
		전송 실패하면 실행될 코드;
		}
});

```
* 보안 정책 : 동일 출처 원칙

* JQuery 플러그인 : script 태그에 붙여서 사용 가능
ex)

```
(function(win,$){
    var $html = $("html");
    var deviceSize = {
        pc : 1009,
        tablet : 801,
        mobile : 800
    };
    var w1 = $html.css({"overlow-y" : "hidden"}).width();
    var w2 = $html.css({"overlow-y" : "scroll"}).width();
    if(w1 - w2 > 0){
        deviceSize.pc -= 17;
        deviceSize.tablet -= 17;
        deviceSize.mobile -= 17;
    }
    $(win).on("resize",function(){
        var w_size = $(win).width();
        if(w_size >= deviceSize.pc){
            $html.removeClass().addClass("pc");
        }else if(w_size < deviceSize.pc && w_size >= deviceSize.tablet){
            $html.removeClass().addClass("tablet");
        } else if(w_size <= deviceSize.mobile){
            $html.removeClass().addClass("mobile");
        }
    });
    $(document).on("mouseover focus", ".pc #member-wrap table tbody tr td .tablet #member-wrap table tbody tr td.mobile #member-wrap table tbody tr td",play);
    $(document).on("click",".mobile #member-wrap table tbody tr td",play);
    function play(){
        var $ts = $(this);
        if($("html").hasClass("mobile")){

        }else{
            $("#member-wrap table tbody tr tdinvisible").slideUp(300);
            $ts.next().stop(true,true).slideDown(300);
        }
    }
}(window,jQuery));
```
