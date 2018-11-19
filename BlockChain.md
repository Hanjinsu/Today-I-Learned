# Block Chain

Definition : 무결한 공개가능한 모든사람이 검증하고 모든사람이 보고있을 수 있는 네트워크

## POW (Proof of Work)

 - Ex) Bitcoin, Light Coin etc..
   Miner 들이 Hash 연산을 처리하여 Nonce 값을 발견하고 Block을 검증한다.

   * Hash : H = h(x) 에서 H 값을 알고 x = previous block hash + transaction + timestamp + nonce(?)

   * 단점 : 느리다 -> 한 블록 당 검증 10분이고 6블록 확정되면 1시간이 걸린다, 아주 큰 cpu power가 필요, multie chain 불가능

## POS (Proof of Stake)

 - Ex) Neo etc..
   해당 코인을 가지고 있는 소유자가 Validator가 되어 보유하고 있는 Stake에 비례하여 블록을 생성할 권한을 나누어 갖는다.

   * 장점 : Hash Power가 많이 필요하지 않아 경제적이며 친환경적, 블록 생산자의 탈중앙화로 인한 안정성 확보, 지분을 담보로 잡아 덤핑 방지
   * 단점 : 시중 코인의 유통량 감소, 검증되지 않아 보안성 취약 가능성, 코인을 많이 보유한 사람이 권력을 진다.
