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

* box-sizing : 박스 모델의  너비, 값 기준 지정 ex) box-sizing:content-box, box-sizing:border-box
* float 속성 : 요소를 왼쪽이나 오른쪽에 떠있게 만듦 ex) float: left | right | none
* clear 속성 : float 속성을 무효화 시킴 clear : none | left | right | both
* position 속성 : position: static | relative | absolute | fixed
  * static : 문서의 흐름대로 배치
  * relative  자연스럽게 배치 -> left, top으로 위치 옮길 수 있다. ex) left:-30px;
  * absolute : 문서의 흐름과는 상관없이 원하는 위치에 배치. 부모 요소 기준. ex) left, top, right, bottom
  * fixed : 문서의 흐름과 상관없이 원하는 위치에 배치. 브라우저 창 기준. ex) 왼쪽 위 (0,0) 기준

* visibility 속성 : 특정 요소를 화면에 보이거나 보이지 않게 설정하는 속성 ex) visibility : visible | hidden | collapse
* z-index 속성 : 요소 쌓는 순서 정하기 z 값이 크면 작은요소보다 위에 쌓임

## 다단 편집

* column-width : 단의 너비를 고정해 놓고 화면 분할
* column-count : 단의 개수를 먼저 정해 놓고 화면 분
* 다단 위치 지정 : 특정 요소의 앞이나 뒤 ex) break-before:column;
* 여러 단을 하나로 합치기 : column-span: 1 | all;

## 표 스타일

* caption-side : 설명글은 기본 위쪽 ex) caption-side: top | bottom
* border : 표의 바깥 테두리와 셀 테두리 모두 지정해야함 ex) td 까지 지정해야함
* border-collapse : 표 테두리와 셀 테두리를 합칠 것인지 설정 ex) border-collapse : collapse | seperate
* border-spacing : 셀을 분리할 경우 셀 사이의 거리 지정 ex) border-spacing : <크기>
* empty-cell : 셀을 분리할 경우 빈 셀들의 표시 여부 ex) emptycells: show | hide
* width, height : 너비나 높이를 지정하지 않으면 셀 안의 내용이 표시될 만큼만 나옴. padding을 주면 이쁨
* table-layout : 셀 안의 내용 양에 따라 셀 너비를 변하게 할지, 고정 시킬지 결정 ex) table= layout : fixed | auto
* text-align : 셀 안에서의 수평 정렬 방법 ex) tet-align : left | rigth | center
* vertical-align : 셀 안에서의 수직 정렬 방법 ex) vertical-align: top | bottom | middle


## HTML4 vs HTML5

* HTML4 는 `<div>` 태그에 맡겨 놓았고 HTML5는 표준화된 시맨틱 태그를 이용해 웹 문서 구조 설정

* 시맨틱 태그 :
 - `<header>` 태그 - 머리말 지정하기. 사이트 전체의 제목, 주로 페이지 맨 위쪽이나 왼쪽. `<form>` 태그로 검색, `<nav>`태그로 사이드 메뉴
 - `<section>` 태그 - 주제별 콘텐츠 영역 : 문서에서 콘텐츠 묶음. `<hm>`태그가 사용
 - `<article>` 태그 - 콘텐츠 내용 : 웹 상의 실제 내용,  태그 적용을 때고 독립적 배포
 - `<aside>` 태그 - 본문 이외의 내용 : 본문 내용 외에 주변에 표시되는 기타
 - `<iframe>` 태그 - 외부 문서 삽입 : 웹 문서 안에 다른 외부 문서 삽
 - `<footer>` 태그 - 제작자 정보와 연락처 정보
 - `<address>` 태그 - 제작자 정보와 연락처 정
 - `<div>` 태그 - 콘텐츠를 묶어 시각적 효과를 적용할 때 사용

## 웹과 멀티미디어 

* 플러그인 프로그램 -> `<object>`, `<embed>` 외부 파일 삽입 ex) `<object data="경로" type="유형" name="이름" width="너비" height="높이"></object>`, `embed src="경로" typ="유형" width="너비" height="높이">`
* HTML5와 비디오 코덱 : encoding, decoging, 비디오 코덱 ex) H.264/AVC, Ogg Theora, v8, v9
* 멀티미디어 웹 표준화 -> 플러그인 프로그램 없이 브라우저 자체에서 멀티미디어 재생. 단, 브라우저마다 차이가 있다.
* HTML5 비디오 변환 -> webm, mp4, ogv 파일 변환 -> firefogg 이용해 webm 파일과 ogv 파일 변환
* `<audio>` : 배경음악이나 효과음 , mp3 파일 사용  ex) `<audio src="오디오 파일 경로" [속성] [속성="속성 값"]></audio>`
* `<video>` : 웹 문서에 비디오 삽입 ex) `<video src= "비디오 파일 경로" [속성] [속성="속성 값"]></video>`
* 속성
 - width, height : 비디오 크기 조절
 - controls : 미디어 파일에 컨트롤 막대 표시
 - preload : 재생하기전에 다운할 것인지, 일부 정보만 다운할 것인지. ex) controls preload= none | metadata | auto;
 - muted : 소리는 끄고 화면만 재생
 - autoplay : 미디어 파일을 다운하자마자 재생
 - loop : 미디어 파일 반복 재생
 - poster : 포스터 이미지 지정


## 오디오 비디오 재생

* `<track>` : 비디오에 외부 자막 파일 연결 태그 ex) `<track kind="자막 종류" src="경로" srclang="언어" label="제목" default>` -> 속성 :  kind, src, label, default
* WebVTT 파일 : 모든 브라우저에서 공식적으로 지원하는 자막 파일 형


## CSS3 선택자

* 연결 선택자 : 선택자와 선택자를 연결해 적용하는 대상을 한정하는 선택자
 - 하위 선택자 : 상위요소 하위요소 -> 부모 요소에 포함된 모든 하위 요소에 스타일 적용 ex) section p { color:blue;}
 - 자식 선택자 : 부모요소 > 자식요소 -> 자식 요소에 스타일을 적용하는 선택자 ex) section > p { color:blue;}
 - 인접 형제 선택자 : 요소1 + 요소2 -> 같은 부모를 가진 형제 요소 중 첫 번째 동생 요소에만 적용 ex) h1 + p { color:blue;}
 - 형제 선택자 : 요소1 ~ 요소2 -> 형제 요소들에 스타일 적용 ex) h1 ~ p { text-decoration : underline;}

* [속성~=값] 선택자 : 지정한 속성을 가진 요소를 찾아 스타일 적용
* [속성|= 값] 선택자 : 주어진 속성과 속성 밧이 일치하는 요소를 찾아 스타일 적용
* [속성^=값] 선택자 : 특정 값으로 시작하는 속성을 가진 요소를 찾아 스타일 적용
* [속성$=값] 선택자 : 특정 값으로 끝나는 속성을 가진 요소를 찾아 스타일 적용
* [속성`*`=값] 선택자 : 값의 일부가 일치하는 속성을 가진 요소를 찾아 스타일 적용

## 가상 클래스와 가상 요소

* :link -> 방문하지 않은 링크에 스타일 적용
* :visited -> 방문한 링크에 스타일 적용
* :activate -> 웹 요소를 활성화 했을 때의 스타일 적용
* :hover -> 웹 요소에 마우스 커서를 올려놓을 때의 스타일 적용
* :focus -> 웹 요소에 초점이 맟주어 졌을 때의 스타일 적용

ex)
```CSS
<style>
  .navi a:link, .navi a:visited{
    padding: 10px 5px 5px 35px;
    display: block;
    color: #fff;
    width: 150pxl
    text-decoration: none;
  }
  .navi a:hover, .navi a:focus{
    text-shadow: 0px 2px 2px *000;
    color: #FC0;
  }
  .navi a:active{
    color: red;
  }
</style>
```
* UI 요소 상태에 따른 가상 클래스 
 - :enabled, :disabled : 요소를 사용할 수 있을 때와 없을 때의 스타일 지정
 - :checked : 라디오 박스나 체크 박스에서 항목을 선택했을 때의 스타일 지정
ex)
```CSS
    <label class="que">
        <input type="radio" name="subject" value="speaking"><span>뀨ㅠㄲ</span>
    </label>
    <label class="que">
         <input type="radio" name="subject" value="grammer"><span>에베</span>
    </label>
    <label class="que">
        <input type="radio" name="subject" value="writing"><span>와더</span>
    </label>

<style>
	input:disabled{
                background:#ddd;
                border:1px #ccc solid;
        }
	.que input:checked + span{
                color:red;
        }
</style>
```

* 구조 가상 클래스
 - :nth-child(n) : 앞에서 부터 n번째 자식 요소에 스타일 적용
 - :nth-last-child(n) : 뒤에서 부터 n번째 자식 요소에 스타일 적용 
```CSS
<table class="git" border="1">
        <tr><td>블루베리</td></tr>
        <tr><td>사과</td></tr>
        <tr><td>귤</td></tr>
        <tr><td>포도</td></tr>
        <tr><td>와인</td></tr>
</table>

<style>
	.git tr:nth-child(2n+1){
                background: lightblue;
                color: black;
        }
</style>
```

 - :nth-of-type(n), :nth-last-of-type : 앞에서 뒤에서 n 번재 요소에 스타일 적용
 - :first-child, :last-child : 첫번째 마지막 자식 요소 스타일 적용 
 - :first-of-type(n), :last-of-type : 형제 요소들 중 첫번째 마지막 요소에 스타일 적용 
 - :only-child, :only-of-type : 유일한 요소에 스타일 적용

* 가상 요소
 - ::first-line : 특정 요소의 첫번째 줄에 스타일 적용
 - ::first-letter : 특정 요소의 첫번째 글자에 스타일 적용
 - ::before : 특정 요소의 앞에 지정한 내용 추가
 - ::after : 특정 요소의 뒤에 지정한 내용 추가

## 변형
-> 특정 요소의 크기나 형태 등 스타일이 바뀌는 것

* translate 함수 :  지정한 방향으로 이동할 거리를 지정하면 해당 요소 이동시킴
 - transform: translate(tx, ty)
 - transfrom: translate3d(tx, ty, tz)

* scale 함수 : 지정한 크기만큼 요소를 확대/축소
 - transform: scale(sx, sy)
 - transform: scale3d(sx, sy, sz)

* rotate 함수 : 각도 만큼 웹 요소를 시계방향이나 시계 반대방향 회전
 - transform : rotate (각도)
 - transfom : rotate3d (2.5, 1.2, -1.5, 45deg)

* skew 함수 : 요소를 지정한 각도만큼 비틀어 왜곡
 - transform : skew(ax, ay);

* transform-origin : 특정 지점을 변형의 기준으로 설정 ex) transform-origin: x, y, z | initial | inherit;
* perspective : 원근감을 갖게함 ex) perspective: 크기 | none;
* perspective-origin : 입체적으로 표현할 요소의 아랫부분 지정 ex) perspective-origin: x | y;
* transform-style : 부모 요소에 적용한 3D 변형을 하위 요소에 적용 ex) transform-style: flat | preserve-3d
* backface-visivility : 요소의 뒷면을 표시할 것인지 결정 

## 트랜지션
-> 웹 요소의 스타일 속성이 조금씩 자연스럽게 바뀌는 것
* transition-property : 대상 설정 ex) transition-property : all | none | 속성이름 
* transition-duration : 진행 시간 ex) transition-timeing-function : linear | ease | ease-in | ease-out etc..
* transition-timing-function : 속도 곡선
* transition-delay : 지연 시간
* transition : 한꺼번에 설정 

## 애니메이션

* @keyframes 속성 : 애니메이션의 시작과 끝을 비롯해 상태가 바뀌는 지점을 설정 ex) @keyframes <이름>{ 선택자{스타일}>
* animation-name 속성 
ex) 
```CSS
div{
  width: 100px;
  height: 100px;
  background-color: blue;
  animation-name : change-bg;
  animation-duration : 3s;
}
@keyframe change-bg{
  from{
   background-color: blue;
   border: 1px solid balck;
  }
  to{
   background-color: #a5d6ff;
   border: 1px solid blue;
   border-radius : 50%;
  }
}
```
* animation-duration : 실행 시간 설정
* animation-direction : 애니메이션이 끝난후 원래 위치로 돌아가거나 반대 방향으로 애니메이션 실행 지정 ex) animation-direction: normal | alternate
* animation-iteration-count : 애니메이션 반복 횟수 지정하기 ex) animation-iteration-count : 숫자 | infinite
* animation-timeing-function : 애니메이션 속도 곡선 지정 ex) animation-timing-function : linear | ease | ease-in | ease-out | etc ..

* **animation** 속성 : 여러 개의 애니메이션 속성을 하나의 속성으로 줄여서 사용 ex) .box{ animation: moving 3s alternate infinite ease-in;}

## 반응형 웹 디자인 
-> 다양한 화면 크기에 반응하여 화면 요소들을 자동으로 바꾸어 사이트 구현

* 뷰포트 viewport : 실제 내용이 표시되는 영역
* 뷰포트 지정하기 : `<head>`태그 안에서 `<meta>`태그를 이용해 뷰포트 지정 ex) `<meta name="viewport" content="width=device-width, initial-scale=1">`

* 그리드 시스템(grid system) : 화면을 여러개의 컬럼으로 나누어 필요할 때마다 재배치하는 방법 (960 그리드, 1200 그리드, 12칼럼 그리드, 16칼럼 그리드)

* 가변 그리드 레이아웃
 - 전체르 감싸는 요소의 너비를 %로 변환
* 가변 글꼴
 - em 단위 : 부모 요소 폰트의 대문자 M 너비를 1em 지정. 1em = 16px
 - rem 단위 : 기본 크기를 지정하고 기준으로 글자 크기 지정 

* 가변 이미지 : 브라우저 창의 너비가 변하더라도 너비 값 조정
 - CSS 활용 : 이미지를 감싸고 있는 부모 만큼만 커지거나 작아지도록 max-width 속성을 100%로 지정
 - `<img>`태그와 srcset 속성 : 너비 값이나 픽셀 밀도에 따라 고해상도 이미지 파일 지정 가능 ex) `<img src="이미지" srcset="이미지1 이미지2 ...">`
 - `<picture>`태그와 `<source>` 태그 : 화면 해상도 뿐 아니라 너비에 따라 다른 이미지 파일 표시

* 가변 비디오 : CSS 사용해 max-width 속성을 100%로 지정 

## 미디어 쿼리
-> 접속하는 장치에 따라 특정한 CSS 스타일 사용하도록 함

* 미디어 쿼리 구문 ex) @media [only | not] 미디어 유형 [and 조건] * [and 조건] -> and, only, not, 쉼표
ex) @media screen and (min-width:200px) and (max-width:360px)

* 미디어 쿼리 조건 
 - 단말기의 가로 너비와 세로 높이 ex) device-width, device-heigth, min-device-width .. 
 - 화면 회전 -> operation 속성으로 화면 방향 체크 
 - 화면 비율 : 단말기 브라우저 화면의 너비 값을 높이 값으로 나눈 것 
 - 단말기 화면 비율 : 화면 비율과 동일
 - 색상당 비트 수 : 단말기의 최대 색상 비트 수를 조건으로 사용
 
* 미디어 쿼리 중단점 만들기
 - 스마트폰 세로 : @media only screen and (min-width: 320px){ ... }
 - 스마트폰 가로 :  @media only screen and (min-width: 480px){ ... }
 - 태블릿 세로 :  @media only screen and (min-width: 768px){ ... }
 - 태블릿 가로, 데스크톱 :  @media only screen and (min-width: 1024px){ ... }

* 외부 css 파일 연결
 - `<link>`태그 사용하기 : `<head>` 태그 사이에 삽입. ex) `<link rel="stylesheet" media="screen and (max-width:768px) " href="css/tablet.css">`
 - @import 구문 사용하기 : `<style>` 태그 사잉에 삽입. ex) @import url("css/tablet.css) only screen adn (max-width:321px) and (maxwidthL768px);
 - 웹 문서에서 직접 정의하기 : `<style media ="미디어 쿼리 조건">`
 - `<style>` 태그 안에 @media 구문 사용하기

## 플렉서블 박스 레이아웃
-> 그리드 레이아웃을 기본으로, 플렉스 박스를 원하는 위치에 배치하는 것

* flex container : 웹 문서를 먼저 플렉스 컨테이너로 묶어줘야한다.
* flex item : 플렉스 컨테이너에 담기는 웹 요소들
* main axis : 컨테이너 안에서 항목을 배치하는 기본 방향. 주축에서 플렉스 항목이 배치되기 시작하는 지점이 시작점 끝이 끝점이다.
* cross axis : 주축과 교차되는 방향. 일반적으로 위에서 아래.

* display 속성 : 배치 요소들을 감싸는  부모 요소를 flex container로 지정 ex) display: flex | inline-lex >>> display 속성에 브라우저 접두사를 붙여야함
* flex-direction 속성 : 플레스 항목 배치 방향 지정 ex) flex-direction: row | row-inverse | column | column-inverse
* flex-wrap 속성 : 플렉스 항목을 한줄 또는 여러줄로 배치 ex) flex-wrap: no-wrap | wrap | wrap-reverse
* flex-flow 속성 : 플레스 배치 방향과 여러 줄 배치를 한꺼번에 지정 ex) flex-low : 플렉스 방향 플렉스 줄 배치
* justify-content 속성 : 플렉스 항목을 주축 방향으로 배치할 때의 배치 기준 ex) justify-content : flex-start | flex-end | center | space-between | space-around
* align-items, align-self 속성 : 교차축을 기준으로 하는 배치 방법 조절 ex) align-items : stretch | flex-start | flex-end | center | baseline
* align-content 속성 : 플레스 항목이 여러 줄로 표시될 때 교차 축 기준의 배치 방법 지정 ex) align-content : flex-start | flex-end | center | space-between | space-around

* felx 속성 : 플렉스 항목의 크기 조절 -> 기본값 flex:0 1 auto; ex) felx : `[<flex-grow> <flex-shrink> <flex-basis>] | auto | initial
ex) 

```CSS
	#box1{
             flex:1 1 0;
         }
        #box2{
             flex:2 2 0;
        }
```
