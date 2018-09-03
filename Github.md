# Today-I-Learned

## 2018-09-03
### GitHub의 Rebase
#### Rebase란? 
* git-rebae : Forward-port local commits to the updated upstream head
* git-merge : Join two or more development histories together

##### 두개의 브랜치로 나누어진 커밋 히스톤리
[commit1](https://git-scm.com/figures/18333fig0327-tn.png)

##### 나뉜 브랜치를 Merge 하기
[commit](https://git-scm.com/figures/18333fig0328-tn.png)

* 실제로 두 브랜치가 나뉘기 전인 공통 commit으로 이동하고 나서 그 commit부터 지금 checkout한 브랜치가 가리키는 commit까지
  임시로 저장한 후 변경 사항 적용하는 방식이다.