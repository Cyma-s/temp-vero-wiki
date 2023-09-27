---
title   : VPC
date    : 2023-06-11 17:19:21 +0900
updated : 2023-06-11 17:19:39 +0900
tags     : 
- 네트워크
- aws
---

## VPC란

Virtual Private Cloud : 가상 프라이빗 클라우드 (논리적 네트워크)

클라우드 컴퓨팅 환경에서 네트워킹을 구성하는 데 사용되는 가상 네트워크이다.   
사용자가 정의한 IP 주소 범위에서 작동하며, 사용자는 서브넷, 라우팅 테이블, 네트워크 게이트웨이 등의 구성 요소를 사용하여 VPC를 세부적으로 관리할 수 있다. 

### 장점

1. 다른 VPC와 완전히 분리된 환경을 제공하여 보안과 개인정보 보호를 강화할 수 있다.
2. 사용자는 VPC 내에서 사용할 IP 주소 범위를 정의할 수 있다. 네트워크 주소 공간을 효율적으로 관리할 수 있다.
3. VPC 내에서 서브넷을 생성하여 리소스를 그룹화하고, 라우팅 테이블을 사용하여 트래픽을 관리할 수 있다. 네트워크 트래픽을 효율적으로 분배하고 제어할 수 있다.


### 참조
- https://docs.aws.amazon.com/ko_kr/vpc/latest/userguide/what-is-amazon-vpc.html