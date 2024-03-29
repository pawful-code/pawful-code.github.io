---
category: bookreview
tags: [bookreview, CleanArchitecture]
usemath: [latex]
---

# Chapter 14
## Overview
 저자는 해당 챕터에서  컴포넌트 사이의 관계를 다루는 3가지 원칙(ADP,SDP,SAP)을 설명한다. 또한 개발 가능성과 논리적 설계사이의 균형을 다룬다. 각 원칙이 왜 필요하며 얼만큼 준수되는지에 대한 지표를 제안하고 개발 주기에 맞추어 각 원칙은 서로에게 '의존성 관리 지표'를 소개하며 지표를 맹신하기 보다 지표를 이용해 유용한 발견을 할 것을 조언한다.

## Key Concepts
"ADP", "SDP", "SAP", "의존성 관리 지표"

## Review

ADP, SDP, SAP, 및 의존성 관리 지표에 대해 설명한다.

### ADP (의존성 비순환 원칙)

컴포넌트 의존성 그래프에 순환(cycle) 이 있어서는 안 된다.

저자는 아키텍처 상에 컴포넌트들의 의존성이 순환 관계에 놓이게 되면 개발팀이 안정된 버전을 빌드하는데 악 영향을 끼칠 수 있다고 주장한다. 의존성 순환 관계에 놓인 컴포넌트들은 개별 컴포넌트들을 각기 다른 개발(팀/자)들이 구현하는 환경에서 치명적일 수 있다. 
저자는 하나의 소스 파일을 여러 개발자가 수정하는 환경에서 발생하는 사례를 예시로 들며 '숙취 증후군' 이라고 명명하였다. 또한 이를 해결하기 위한 두 가지 해결법인 '주 단위 빌드'와 '의존성 비순환 원칙'을 소개한다. 또한 컴포넌트가 순환 관계에 놓여 있을 때 '주 단위 빌드'가 가지는 한계점을 보인다.

### 주 단위 빌드
개발 환경: 각 개발 조직이  개발을 한 후 금요일에 통합(빅뱅 통합)
소프트웨어의 규모가 커지고 순환성이 발생하면 개발에 필요한 컴포넌트 버전을 맞추거나 하기 위해  격주로 통합을 하거나 하는 등 통합의 일정이 늦어지는 현상이 발생하고 결국 빌드 일정이 계속 늘어나 빠른 피드백을 받을 수 없게 되어 프로젝트가 무산될 위기에 처한다.

### 순환 의존성 제거하기
개발환경 : 릴리스 가능한 컴포넌트 단위로 분리한다.
 개별 개발(팀/자)이 각자 담당하는 컴포넌트를 릴리스 하여 다른 개발자가 사용할 수 있도록 만든다. 또한 이러한 릴리스에 릴리스 번호를 부여하고, 다른 팀에서 사용할 수 있는 디렉터리로 이동시킨다. 
이 방법이 성공적으로 동작 하려면 컴포넌트 사이의 의존성 구조를 반드시 관리 해야한다. 의존성 구조에 순환이 생기면 '숙취 증후군을 피해 갈 수 없다. 순환 의존성이 있는 컴포넌트들은 하나의 컴포넌트 덩어리가 되어 버린다.
 이는 다음과 같은 문제를 야기한다.
- 개별 컴포넌트들과 연관된 개발팀들이 연관된 컴포넌트들을 항상 정확하게 동일한 릴리스를 사용해 개발 해야되는 문제를 발생시킨다. 
-  컴포넌트를 분리하기 힘들어지게 되어 빌드관련 이슈가 발생하기 쉬워진다. (원인) 분리하기 어려운 컴포넌트로 인해 단위 테스트를 수행하고 릴리스 하는 일이 어려워지고 에러도 쉽게 발생하며 모듈이 증가함에 따라 기하 급수적으로 증가하며 컴포넌트를 어떤 순서로 빌드 해야할 지 파악하기 힘들어진다.

