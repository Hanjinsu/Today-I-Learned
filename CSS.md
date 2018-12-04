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
