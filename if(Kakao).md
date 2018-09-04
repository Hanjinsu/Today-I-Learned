#if Kakao

## 맵매칭(부정확한 GPS포인트들로부터 경로 추정하기) *김상균(curt.k)/카카오모빌리티*

### gps를 받아 도로네트웤에 매칭 -> 노드와 링크로 이루어짐
*1. 버스/내비처럼 정해지 경로를 가정 -> 
*2. 정해진 경로가 없이 네트웍 가정 : 가장 가까운 노드에 붙이면 x, 가장 가까운 링크 x(확률의 문제), 링크에 붙이고 여러 후보를 유지 및 이전 포인트와 관계 고려
*3. emission 확률(parameter = 25m) 정규분포
*4. transition 확률(condidate 사이의 확률) 지수분포
*5. 그래프를 그려 확률 조사. -> 후보점이 늘어날 수록 찾아야할 경우의 수가 많아짐 -> dynamic programming으로 개선(확률 누적))
*6. memory 문제 -> window를 나눈다 ->  
*7. GPS튀는 현상 -> 속도와 GPS위치를 검토하여 필요없는 데이터를 버림
*8. 맵매칭이후 중복제거 
**prefilter -> MapMatcher-> PostFilter**
> viterbi Algorithm 

## Query by Image(이미지로 이미지 검색하기) *이주영(michael.lee)/카카오*
* id = 55575 data set 
* 사진을 표현하는 문장이 필요
* distance(Ia,Ip) < distance(Ia,Ip)


## 딥러닝을 이용한 얼굴인식 *신종주(issac.shin)/kakao corn*

*1. 얼굴 검출(이미지에서 얼굴 추출
*2. 눈코입 등 특정 부위 탐색
*3. 정규화
*4. 인지 -> gallery(db)
* LFW
* Triplet loss(2015), Contrastive loss(2014), Center loss(2016), Ring loss(2018)
* NormFace(2017), Sphere Face(2017), cosFace(2018), ArcFace(2017)
**margin을 어디에 붙이느냐로 이름이 결정**
* MSCeleb-1M(2016) 10만명,1000만장  - VGGFace2(2018) 9131명, 331만장
> davidsandberg/facenet, deepinsight/insightface (Git)

## 지식그래프

*1. 기존의 검색 : ex) 문서에 모든 정보 저장 -> mapping -> 뿌려줌
*2. 지식그래프에서 검색어의 의미 ->  카카오(회사 카카오), 서비스(카카오의 서비스 ->  검색어의 의미 부여 
*3. 지식그래프의 연결(도메인의 구분이 없이 연결) -> 카카오 : 인물, 장소, 책, 축구, 자동차 등등 (12억번) fact 기반, 관계기반, 위치기반
*4. 트와이스 리더 나이가 몇이야? -> 음성인식, 도메인 분류(인물,리더 등 속성),정보검색 봇 -> Cruise QA -> Cruise QL -> Criose KG (Mobydic - 동의어를 모두 갖고 있음), Defiant(추론시스템)
 트와이스 리더 나이 -> object, property 분류 -> 쿼리 생성 : Cruise QL(카카오의 db 정의) 지식 그래프 탐색 -> 공통 검색 가능
*5. 같은 객체 찾기 
*6. 외부 데이터 연결 확장, 광고와 서비스 연결, 지식그래프의 추천 및 개인화

## 눈으로 듣는 음악 추천 시스템 *최규민(pi.314)kakao.corp*

*1. song vector 하나의 vector 공간에 song 을 embading -> 고차원의 vector : melon의 데이터 이용
*2. 유저가 노래를 듣는 방법 : 기호에 맞는 노래 -> 장르, 발매년도 
*3. 유저 벡터 X 아이템 벡터 
*4. sampling, dimension, song meta mapping, song segmentation
*5. matrix factorization < word2vec

## TOROS

*1. 벡터모델, embading
*2. K-Nearest Neighbor -> 찾아야 하는 것을 벡터로 표현 한 뒤, 인접한 이웃을 찾아주면 끝 (질문 : N개의 data가 있을때 몇개의 차원이 가장 적합?)
*3. 시간이 오래걸려 정확도를 근사하여 속도를 get 한다. -> Approximate KNN
>[Github](http://github.com/erikbern/ann-benchmarks#glove-100-angular)
*4. 90% 정확도로 100배 빠르게 찾을 수 있다.
> annoy : github.com/spotify/anoy -> hyper parameter, 사용하기 쉬움, MMAP 지원
> nmslib : github.com/nmslib/nmslib -> 우수한 HNSW 알고리즘 지원, MMAP 미지원
TOROS N2 : github.com/kakao/n2
**HNSW** : H x NWS -> 아래로 갈수록 노드 밀집도 증가, 노드간 거리 감소 -> 큰 곳에서 먼저 찾고 내려오면서 점점 세분화


## 뉴스메타 태깅

 *1. 기사 형태 분류 하기
 사실 전달형 기사 -> 육하원칙 위주, 해설/묘사형 기사 -> 사건, 인물을 심층 취재
 * Character based Convolution Newral Network -> 형태소, Embedding 제외하고 character 단위 처리, 한글, 한자, Roman 등 처리, 문자와 단어의 순서 보존하여 기사의 문투 학습
 * 정답셋이 필요 -> 근사기준 : ex) 기사의 길이 , 보완책 : 뉴스 전문가, 샘플 학습 데이터, 테스트 데이터 
 * 60char와 1014char 두가지 모델을 합쳐서 정확도를 올림
 *2. 뉴스 메타 태깅 시스템
 뉴스 발행 후 메타데이터를 생성하고 유통시키는 플랫폼
 * 메타 데이터의 생성과 소비가 함꼐 이루어지느 흐름
 news topic -> 메타데이터 생성 서비스 -> tag topic
 * Inferrer API -> Ensemble API(merge) : filtering -> invoke ensemble -> Post-process -> produce 의 반복
 