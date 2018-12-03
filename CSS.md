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
