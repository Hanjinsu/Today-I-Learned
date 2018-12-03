# CSS
 
## 스타일 스타일 시트 

* style : html 문서에서 자주 사용하는 글꼴이나 색상, 정렬, 각 요소들의 배치 방법 및 겉모습 결정
* style sheet : 스타일을 관리하기 쉽도록 한군데 모아놓은 것

* style 형식 -> p 선택자  { text-align 스타일 속성 : center 속성 값; } 
ex)
~~~
h2{font-size:20px; color:orange;}
~~~

* 내부 style 태그는 head 태그 안에서 정의
* 외부 style 태그는 link 태그만 사용해 미리 만들어 놓은 외부 시트에 연
* 인라인 style은 적용하고 싶은 태그에 바로 적용 

## 주요 선택자

* 전체 선택자 : 페이지에 있는 모든 요소를 대상으로 스타일 적용할 때 사용
ex)
```CSS
* {
    margin:0;
    padding:0;
     }
```

* 태그 선택자 : 문서에서 특정 태그를 사용한 모든 요소에 스타일 적용
  ex ) 태그 {스타일}

* class 선택자, id 선택자 : 문서안에서 여러번이면 class, 한번이면 id
ex)
 * class 선택자
```CSS
.bluetext{
 color:blue;
}
```
 * id 선택자
```CSS
#container{
  background: #ff6a00;
}
```
* 그룹 선택자 : 같은 스타일을 사용하는 선택자를 한꺼번에 정의ㅣ
ex ) h1,h2 {스타일}

## Cascading Style Sheets

* 스타일 우선숭위 - 스타일 규칙의 중요도, 적용 범위에 따라 우선순위가 결정되고 위에서 아리로 스타일 적용
* 인라인 스타일 -> id 스타일 -> 클래스 스타일 -> 태그 스타
* 소스에서 나중에 온 스타일이 먼저 온 스타일을 덮어

## 글꼴 관련 스타일

* font-family 속성 ex) body{ font-family : "맑은 고딕", 돋움, 굴림 }
* font-face 속성 web-font -> 웹 문서안에 글꼴을 함께 저장해 사용자가 없더라도 의도한대로 표시 가능
ex) @import url(http.~~~~.css);
* font-size 속성:  ex) p{ font-size:20px; }
* color 속성 : ex) h1 {color:rgb(0.200,0);},  h1 {color:#ff0000;}, etc...
* text-shadow 속성 : ex) text-shadow: 5px 5px 3px #f00);}

## 문단 목록 관련 스타일 

* white-space 속성 : ex) .letter1{ letter-spacing: 0.2em;}
* text-indent 속성 : 문단의 첫 글자를 들여쓰는 방법 ex) .indent {text-indent:15ps;}
* line-height 속성 : 문단의 줄 간격 지정 ex) .big-line {line-height:2;} (글자크기 기준)
* list-style-type 속성 : 순서 없는 목록의 블릿이나 순서 목록의 숫자를 바꾸는 속성 
* list-style-image 속성 : 순서 없는 목록의 블릿을 이미지로 바꿈
* list-style-position : 블릿이나 번호를 들여쓰거나 내어쓸 수 있다.

## 색상과 배경

* 16진수 표기법 : #fffff 앞에서 두자리씩 빨강, 초록, 파랑의 양
* hsl/hsla : color:hsl(240,100%,50%) 색상, 채도, 밝기의 양
* rgb/rgba : color:rgb(255,0,0) 빨강, 초록, 파랑의 양
* 색상 표기 : 기본 색상 16가지 모두 216개
* background-color : ex) background-color:#0094ff
* background-clip : 배경을 어디까지 적용할 지 지정

ex)

```CSS
.bg1{ background-clip:border-box;}
.bg1{ background-clip:padding-box;}
.bg1{ background-clip:content-box;}
```
* background-image : 배경 이미지 지정하기, 이미지 파일 경로 지정 ex) background-image:url(경로)
* background-repeat : 배경 이미지 반복 여부 및 반복 방향 ex) background-repeat : repeat | repeat-x | repeat-y | no-repeat
* background-size : background-size auto | contains | cover | <크기 값> | <백분율>
* background-position : 배경 이미지를 반복하지 않을 경우, 배경 이미지를 표시할 위치 지정
* background-attachment : 배경 이미지 고정 ex) background-attachment:fixed;
* 그라데이션 효과 : 
ex) 
```CSS
<style>
  .grad{
      background : blue;
      background : -webkit-linear-gradient(left top, blue, white);
      background : -moz-linear-gradient(right bottom, blue, white);
      background : -o-linear-gradient(right bottom, blue, white);
      background : linear-gradient(to right bottom, blue, white);
   }
</style>
```
* 그라데이션 각도 : ex) background: linear-gradient(45deg,#ff0000,#ffffff);
* 선형 그라데이션 : 색상 중지점 ex) linear-gradient(to bottom, #06f, white 30%, #06f);
* 원형 그라데이션 : radial-gradient(<최종 모양> <크기> at <위치>, color-stop, [color-stop ..])

## CSS와 박스 모델

* 블록 레벨 요소 : 요소를 삽입했을 때 혼자 한 줄을 차지하는 요소 ex) div, p
* 인라인 레벨 요소 : 줄을 차지하지 않는 요소 ex) img, strong
* 박스 모델 : 실제 콘텐츠 영역, 패딩, 테두리, 마진 등 요소로 구성
* width, height 속성 : 실제 콘텐츠 영역의 크기 지정
* display 속성 : 블록 레벨 요소를 인라인 레벨 요소로 바꾸거나 인라인 레벨 요소를 블록 레벨 요소로 바꿈 ex) display: none | contetns | block | inline-block etc..

## 테두리와 여백 

* border-style : 테두리 종료 border-style: none | hidden | dashed | dotted | double | groove | inset | outset etc
* border-width : 테두리 두께
* border-color : 테두리 색상 
* border : 테두리 스타일, 두께, 색상 묶어 표기 ex) border: 2px dotted black;
* border-radius : 박스 모서리 부분을 둥글게
* box-shadow : 선택한 요소에 그림자 효과 내기 ex) box-shadow : none | <그림자 값>

* margin : 현재 요소 주변의 여백, 요소와 요소간의 간격 조절 가능 ex) margin : <크기> | <백분율> | auto
* padding : 콘텐츠 영역과 테두리 사이의 여백 ex) padding: <크기> | <백분율> | auto

## CSS 포지셔닝 


