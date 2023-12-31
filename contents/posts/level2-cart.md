---
title   : 레벨2 장바구니 미션
date    : 2023-05-14 14:55:27 +0900
updated : 2023-05-14 14:55:49 +0900
tags     : 
- 레벨2
- 미션
- 우테코
---
## 2단계 리뷰

- 혹시 Index를 걸면 좋을만한 것들을 고민해보셨을까요?
	- index란 추가적인 쓰기 작업과 저장공간을 활용하여 DB 테이블의 검색 속도를 향상시키기 위한 자료구조이다. 조회 뿐만 아니라 update, delete의 성능이 함께 향상된다.
	- create, delete, update가 빈번한 속성에 인덱스를 걸게 되면 인덱스의 크기가 비대해져 성능이 저하되는 역효과가 발생할 수 있다.
	- 복합 인덱스는 join, select 쿼리에 유용할 수 있다. mysql에서는 최대 16 column까지 인덱스를 정의할 수 있다. 
	- where 절에서 참조되거나 join 절에서 사용되는 필요한 column을 기준으로 인덱싱해야 한다.
	- 키가 아닌 인덱스 열을 너무 많이 추가하게 되면 인덱스를 저장하는데 더 많은 디스크 공간이 필요하다.
	- 쿼리 성능의 이득이 데이터 수정 중 성능에 미치는 영향과 추가 디스크 공간 요구 사항보다 더 큰지 판단하는 것이 중요하다. 모든 열을 인덱싱하고 싶을 수 있지만, 불필요한 것은 추가하지 않는 것이 좋다.
- create, update, delete가 빈번한 column에 index를 걸면 안 되는 이유?
	- 자주 업데이트되는 column을 인덱싱하면 인덱스 조각화가 발생할 수 있다. (인덱스 페이지가 연속적이지 않다는 것) 데이터베이스는 데이터를 검색하기 위해 추가 I/O 작업을 수행해야 한다. 따라서 인덱스를 사용하는 쿼리의 성능이 저하될 수 있다.
	- 인덱스 조각화란? 인덱스에 있는 페이지의 논리적 순서가 데이터 파일의 페이지의 물리적 순서와 일치하지 않을 때 발생하는 상태이다. 인덱스를 스캔할 때 성능 문제를 일으킬 수 있다. 
	- 자주 업데이트 되는 column을 인덱싱하면 페이지 분할 가능성이 높아질 수 있다. 이미 꽉 찬 페이지에 새 레코드가 삽입되면 페이지를 두 페이지로 분할해야 하며, 디스크 I/O가 추가되고 성능이 저하될 수 있다.
	- 디스크 공간 사용량이 증가한다.
	- 자주 업데이트되지만 검색 빈도도 높은 column의 경우 해당 column을 인덱싱하면 쿼리 성능이 개선된다. 따라서 상황에 따라서는 자주 업데이트되는 column을 인덱싱하는 것이 도움이 될 수도 있다.
- 페이지가 꽉 찼을 때 새로운 데이터가 추가되는 경우에는 기존 페이지의 데이터 절반을 새로운 페이지에 할당한다. 따라서 페이지 밀도가 100%에서 50%로 줄어들게 된다.