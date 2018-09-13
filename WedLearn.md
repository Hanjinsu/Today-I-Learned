# Wednesday Knowledge society

## 20180801

### 선종님
- Ethereaum node discovery
Node 의 구조체를 만들기 위한 hash 함수 SHA-2,SHA-3 있는데 어떤 걸 써야 하는가. Hash 충돌(역성저항성 : 원래 값을 찾아내는 것, 뿐아니라 같은 것이 아니어도 같은 값을 내는 것을 찾는 것) node ID 는 Public Key 로 제공되기 때문에 만약 주지 않는다면 알 수 없다.
이더리움 : bootnode가 모든 node 정보를 갖고잇는다. 근접한 table을 사용하여 routing table 정보 생성
그룹에서 서로소인 부분들을 찾아서 trigger 그래야 배수로 뛰지 않어서 다음이랑 전이 누군지 알 수 없게함
부스트램 어원 : trigger를 pool에서 누구 먼저 시작할 것인가

### 주연님
Pos, DPos 는 합의하는 컨센서스
컨센서스 프로토콜 + 신원위조 방지 메커니즘 (Sypil Attack)
Sybil Attack => 많은 블록을 만들어 영향력을 높여 공격
미트코인 -POW : 가장 긴 체인을 선택한다. 악의적인 노드가 있을 떼 확률적으로만 대응할 수 있다. 6개로 한정 -> 51% 공격(Hash Power가 높아야함) POS는 long-range attack 이라고 한다.
DPos : 지분에 따른 영향력 차이. 지분을 갖고 있다고 모든 블록을 결정하는데 합의하는 것이아님. 투표를 통해 선출됨. 성능 확장성 전력 소모량, 보안성. 다른 layer와 상호작용

### 동혁님 
비잔티움 장군 문제 : 51% 해쉬파워 이상 나오면 공격가능
Byzantine fault tolerance BFT :  N > 3f 일때 일때 방어 가능
다른데에도 널리 쓰일 수 있는 중요한 문제

- 아샬님
BFT 는 최소한의 숫자가 필요하지만  nakamoto consensus는 
1개만 살아나도 전부 살아난다.

## 20180808

### 호건님
Smart Contract (코드 내부에서 결제를 진행)
요소 - turing complete(, 개발자에게 친숙한 언어제공, API 제공 
Solidity : 이더리움 네트워크 안에서 개발할 수 있는 언어
발전 : 다수의 언어 지원, 배포 이후 수정 가능(version control)

### 아샬님
Escrow Arbitration :chain 밖에서 일어나는 일을 어떻게 해결할 것인가
Multi Sig : 3명 중에 2명이 동의하면 가능(A,B,C public key) -> 돈을 보내는 사람이 수술료를 많이 부담
P2SP : unlock에서 다중스크립트를 쓰게함. 스크립트의 해쉬값을 뽑아서 
  1. Complet 2. Full Refund
  

## 20180829

### vim의 역사와 사용방법
	vi -u NONE -N : 아무 옵션없이 실행
	y  : 붙여넣기
	q : record 매크로 끝낼때 @q 숫자 넣으면 그 만큼 매크로
	gg : 꼭대기
	set incsearch : 검색
	set hlsearch : highlight
	g/\v^(\s\s+)\1+
  Lf : Line Feed (옛날 타자기 줄내림)
  Cf : Carriage Return (옛날 타자기 줄내리고 종이 옮김)
  
  
## 20180913

### 선종님
- Func Fatal : 에러로그 출력 및 완전히 종료
- Func Panic : 로그를 출력한 뒤 panic()호출, runtime error 발생, defer로 정의된 함수를 호출한 후 종료, recover 함수를 만나면 제거 후 동작
               (call stack 출력)
               
### 아샬님
- BDD : 실패하는 테스트 -> refactoring -> green
- Bug : 최초의 bug는 컴퓨터 속 벌레로 부터 시작, unexpacted, specification
- Feature == Behavior

### 지원님
- 선형대수학 기초
- 행렬을 바라보는 관점 3가지 : 연립방정식, 공간->공간으로 변환 함수, 기저
- 기저 : 독립적인 벡터로 개수가 n개 이면 n차원 표현 가능
