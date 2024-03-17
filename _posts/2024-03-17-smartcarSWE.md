---
category: demo
tags: [Automotive SWE]
usemath: [latex, ascii]
---

## book review
해당 책은 현대오트론(현대오토에버)의 연구원들과 만도 연구원이 집필한 책이다. 2013년에 출판된 책으로 자동차 업계에 입문하는 자들에게 SW 개발 방식을 이해하기 위한 좋은 가이드이다. autosar 가 classic + adaptive로 나뉘어진 지금에서는 책의 내용과 바뀐 점이 많이 있지만 자동차 업계의 SW가 어떻게 바뀌어 왔는지 현재 와 비교해보며 읽어보기를 추천한다.

## Autosar

### 고전적인 개발 방법
HW선정 이전
evaluation board -> Application SW (ASW)를 위한 기본적인 입출력 신호가 정의된 BSW를 만든다.
HW 선정 이후
BSW & HW 통합 테스트 -> ASW 개발 시작

#### 문제점
HW가 변경되면 BSW를 다시 개발해야하는 문제가 발생. 
문제의 원인 : SW가 HW에 Dependency가 존재하였고 이로 인해 HW 변경으로 포팅을 진행할 시 주로 MCAL영역에서 재작업이 필요하였다. MCAL영역에 재 작업으로 인해 Service layer의 수정도 불가피하였다.

### autosar의 범위
소프트웨어의 이식성 , 재사용성을 높이기 위하여 제작된 표준.
autosar는 아키텍처, 방법론, ASW 인터페이스 등으로 구성되어있다.(2013)

