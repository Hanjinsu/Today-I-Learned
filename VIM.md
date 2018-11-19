# VIM 사용법

## set

* set number : 줄번호 생성
* set indent : 자동 인덴타
* set incsearch : 검색 문자열의 첫번째 문자를 입력할 때 부터 검색 시작
* colorcheme : VIM의 색깔 변경 가능
* set mouse=a : akdntm 커서 이용 가능
> .vimc 파일을 수정해주면 VIM을 사용할 때 모두 적용

## use

* 0 : 현재라인 가장 앞으로 커서 이동
* ^ : 현재라인 가장 첫번째 글자로 커서 이동
* $ : 현재라인 가장 마지막 글자로 커서 이동
* w : 단어단위 앞으로 커서 이동
* b : 단어단위 뒤로 커서 이동
* f : ; -> 다음 검색결과로 점프, , : 이전 검색결과로 점프
* F : 뒤로 검색
* h, j, k, l : 각각 <-, 아래, 위, -> 방향키와 동일
* d : 삭제 -> dd 한 줄 삭제
* u : 이전 작업 복구(undo)
* ^r : redo
* / : 검색 (정규식 사용가능 - VIM 정규식, /\v를 쓰면 perl 정규식 사용가능) n, N으로 search
* ? : 역방향 검색
* v : 비주얼 모드 -> V 한 줄 비주얼 모드(visual mode에서 o를 누르면 시작부분 수정가능, I를 누르면 전부 수정 가능)
* y : 복사 -> yy 한 줄 복사
* p : 붙여넣기 -> P 커서 앞으로 붙여넣기
* ^f, ^b : 페이지 down, 페이지 up
* (number) gg : 줄번호 이동 - 혼자 쓰면 파일의 시작점으로 커서 이동
* (number) G : 뒤로 줄번호 이동 - 혼자 쓰면 파일의 마지막으로 커서 이동
* g : ; -> 마지막 편집점으로 이동