#HTML

## 기본 문서 구조

* `<!doctype html>` : 문서가 HTML5로 작성되었다
* `<html> ~ </html>` : 웹 문서의 시작과 끝
* `<head> ~ </head>` : 웹 문서를 해석하기 위한 정보
* `<body> ~ </body>` : 실제로 나타나는 화면
* `<title>` 태그 : 브라우저의 제목 표시줄에 표시
* `<meta>`  태그 : 문자 인코딩 방법 및 문서 키워드 요약정보
* `<hn> ~ </hn>` : 콘텐츠 영역에서 제목을 표시
* `<p> ~ </p>` : 앞뒤로 빈 줄이 생기며 텍스트 단락
* `<br>` : 줄을 바꿀 때 사용. 닫는 태그 없음
* `<blockquote>` : 다른 텍스트보다 안으로 들여써짐
* `<hr>` : 수평 줄
* `<pre> ~ </pre>` : 소스에 표시한 공
* `<strong>, <b>`: 굵게 표시
* `<em>, <i>` : 이탤릭체
* `<q>` : 줄바꿈 없이 인용표시. "" 추가됨
* `<mark>` : 형광펜 효과
* `<span>, <div>` : 영역 묶기. 인라인, 블록 -> CSS
* `<ul>, <li>` : 순서 없는 목록 -> CSS의 list-style-type 속성으로 불릿 수정
* `<ol>, <li>` : 순서 목룍. 숫자가 붙여짐
* `<dl> , <dt>, <dd>` : 제목, 설명 

## 표

* `<table> ~ </table> `: 표 전체
* `<tr> ~ </tr>` : 행
* `<td> ~ </td>` : 셀
* `<th> ~ </th>`: 제목 셀

 ex) 
~~~
 <table>
    <tr>
      <th>1행 1열(제목)</th>
      <td>1행 2열</th>
      <td>1행 3열</td>
    </tr>
    <tr>
      <th>2행 1열(제목)</th>
    </tr>
 </table>
~~~

* `<td colspan>` : 행 합치기 
* `<td rowspan>` : 열 합치기 

ex)
~~~
 <td colspan="3"></td>
~~~

* `<thead>, <tbody>, <tfoot>` : 표 구조 정의하기
* `<col>, <colgroup>` : 열끼리 묶어 스타일 지정

ex)
~~~
<colgroup>
 <col>
 <col span="2" style="background-color:blue;">
 <col style="background-color:yellow">
</colgroup>
~~~

## 이미지, 링크  

* `<img> `: 웹 문서에 이미지 삽입 -> GIF, JPG/JPEG, PNG
ex)
~~~
<img src="경로" [속성="값"]>
<img src="images/road.jpg", alt="">
~~~

* src : 웹 문서파일의 위치, 웹 이미지 주소 가능
* alt : 이미지 설명 대체 텍스트
* width, height : 이미지 크기 조정(파일의 용량은 그대로)

* `<figure>, <figcaption>` : 이미지에 설명글 붙이기
ex)
~~~
<figure>
   <img src = "images/load.jpg", alt="blabla">
   <figcaption> bla bla bla </figcaption>
</figure>
~~~

* `<a href="링크주소" [속성="속성 값"]> 텍스트 </a>`

* 속성 : href-> 링크한 문서나 사이트
       target -> 링크한 내용이 표시할 창 (새탭에서 링크열기)
       download -> 링크한 내용 다운로드
       ref -> 현재문서와 링크문서의 관계

* 한페이지 안에서 점프하기 - 앵커 : 
ex)
~~~
<ul id="menu">
  <li><a href="#content1">메뉴1</a></li>
  <li><a href="#content2">메뉴2</a></li>
  <li><a href="#content3">메뉴3</a></li>
</ul>
  <h2 id="content1">내용</h2>
  <p><a href="#menu">[메뉴로]</a><p>
~~~

* `<area>`, usemap 속성 - 이미지 맵

## 폼 만들기

* `<form [속성="속성 값"] > 여러 폼 요소 </form>`
- method, name, action, target

ex)
~~~
<form action="search.php" method="post">
  <input type="text" title="검색">
  <input type="submit" value="검색">
</form>
~~~

* `<lable> ; 폼 요소에 레이블을 붙이는 태그. 체크 박스 버튼 등이 생성. 로그인 창 등`
* `<lable [속성="속성 값"] > 레이블 <input ,.> </lable>`

* `<fieldset> ; 폼 요소를 그룸으로 묶는다.`

* `<input> ; <input type="유형" [속성="속성 값"]>`
* `<input type="text" id="user-name" size="10">`
* type -> hidden, text, password, search, url, email, tel, number, range, radio, checkbox, color, data, month, week, time, datetime-local, submit, reset, image, autofocus, placeholder, readonly, required
* `<input> 태그의 다양한 속성` ; min, max, step, size, minlengh, maxlength

* `여러 데이터 나열해 보여주기 <select>, <optgroup>, <option>. <datalist>, <option>, <textarea>`
* 기타 요소들 -> `<button> 버튼, <output> 계산 결과 표시, <progress> 작업 진행 상태, <meter> 용량 표
