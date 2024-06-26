---
layout: post
title: Git과 Github의 차이점
date: 2024-06-25 10:00 +0900
description: Git과 Github의 차이점
image: https://github.com/Hyeji1364/class2024/assets/161557112/eef26b59-f07f-4d11-8702-f905bb1cb345
category: ETC
tags: React Vue
published: true
sitemap: true
---

# Git과 Github의 차이점 : 버전관리와 협업의 핵심 도구

소프트웨어 개발에서 버전 관리는 매우 중요합니다. <br>
이를 위해 널리 사용되는 도구 중 하나가 깃(Git)이며, 깃을 중심으로 한 협업 플랫폼이 깃허브(GitHub)입니다.<br>
이 두 가지는 많은 개발자들에게 필수적인 도구로 자리 잡고 있지만, 그 목적과 기능에서 차이점이 있습니다.<br>
이번 글에서는 깃과 깃허브의 차이점을 명확히 알아보고, 각각의 특징과 사용 방법을 살펴보겠습니다.
<br>

## 💛 깃(Git)의 개념과 주요 특징

깃(Git)은 분산 버전 관리 시스템(DVCS)입니다. <br>
리누스 토르발스(Linus Torvalds)가 리눅스 커널 개발을 위해 2005년에 만든 이 도구는 코드의 변경 이력을 관리하고, 여러 개발자가 동시에 작업할 수 있도록 도와줍니다.
<br>

### 깃의 주요 특징

#### 01. 분산 버전 관리

깃은 중앙 서버 없이도 모든 개발자가 전체 코드 이력을 로컬 저장소에 복제하여 작업할 수 있습니다. <br>
이는 네트워크 문제나 서버 장애 시에도 개발이 계속될 수 있음을 의미합니다.
<br>

#### 02. 브랜칭과 머징

깃은 브랜치를 쉽게 만들고 병합하는 기능을 제공합니다. <br>
이를 통해 개발자는 새로운 기능이나 버그 수정을 독립적으로 진행한 후, 메인 코드베이스에 통합할 수 있습니다.
<br>

#### 03. 빠른 속도와 효율성

깃은 코드 변경 이력 관리를 매우 빠르게 수행할 수 있으며, 효율적인 데이터 압축 방식을 사용합니다.

## 깃의 기본 명령어

- `git init`: 새로운 깃 저장소를 초기화합니다.
- `git clone [URL]` : 원격 저장소를 로컬로 복제합니다.
- `git add [파일명]` : 변경된 파일을 스테이징 영역에 추가합니다.
- `git commit -m "[메시지]"` : 스테이징 영역의 변경 사항을 커밋합니다.
- `git push`: 로컬 커밋을 원격 저장소에 업로드합니다.
- `git pull`: 원격 저장소의 변경 사항을 로컬로 가져옵니다.

<br>

## 💛 깃허브(GitHub)의 개념과 주요 특징

깃허브(GitHub)는 깃 레퍼지토리를 인터넷상에서 제공하는 호스팅 서비스입니다. <br>
깃허브는 코드 저장소를 호스팅하고, 개발자들이 협업할 수 있는 다양한 도구와 기능을 제공합니다. <br>
마이크로소프트가 2018년에 인수한 이 플랫폼은 오픈 소스 프로젝트와 상업적 프로젝트 모두에 널리 사용되고 있습니다.
<br>

### 깃허브의 주요 특징

#### 01. 호스팅 서비스

깃허브는 깃 저장소를 웹에 호스팅하여, 개발자들이 인터넷을 통해 코드에 접근하고 협업할 수 있도록 합니다.
<br>

#### 02. 협업 도구

깃허브는 풀 리퀘스트(Pull Request), 이슈 트래킹(Issue Tracking), 프로젝트 보드(Project Boards) 등 다양한 협업 도구를 제공합니다. <br>
이를 통해 팀원 간의 코드 리뷰, 버그 관리, 작업 계획을 효율적으로 수행할 수 있습니다.
<br>

#### 03. CI/CD 통합

깃허브는 여러 지속적 통합/지속적 배포(CI/CD) 도구와 통합되어, 코드 변경 시 자동으로 빌드 및 테스트를 실행할 수 있습니다.
<br>

#### 04. 오픈 소스 기여

깃허브는 수많은 오픈 소스 프로젝트의 중심지로, 개발자들이 쉽게 프로젝트를 발견하고 기여할 수 있는 환경을 제공합니다.

<br>

### 깃허브 사용 방법

- 저장소 생성: 프로젝트를 호스팅할 새로운 저장소를 생성할 수 있습니다.
- 풀 리퀘스트: 코드 변경 사항을 제안하고, 리뷰어가 이를 검토하여 병합할 수 있습니다.
- 이슈 트래킹: 버그나 새로운 기능 요청을 관리할 수 있습니다.
- 위키: 프로젝트 문서를 작성하고 관리할 수 있습니다.

<br>

## 깃과 깃허브의 차이점 💟

1.  목적
    깃은 `버전 관리 시스템`으로, 로컬 저장소에서 코드 변경 이력을 관리합니다. <br>
    반면, 깃허브는 깃 저장소를 호스팅하고, `웹 기반의 협업 도구`를 제공합니다.

2.  호스팅
    깃은 로컬 컴퓨터에 저장소를 생성하고 관리합니다. 깃허브는 인터넷 상에서 깃 저장소를 호스팅하여, 개발자들이 원격으로 접근할 수 있습니다.

3.  기능
    깃은 기본적인 버전 관리 기능을 제공합니다. 깃허브는 여기에 추가로 협업 도구, CI/CD 통합, 오픈 소스 기여 환경 등을 제공합니다.

<br>

## 결론 ✨

깃과 깃허브는 각각 다른 목적과 기능을 가진 도구이지만, 함께 사용될 때 강력한 시너지를 발휘합니다. <br>
깃은 로컬에서 버전 관리를 효율적으로 수행할 수 있게 해주고, 깃허브는 이를 바탕으로 원격에서 협업을 원활하게 할 수 있도록 지원합니다. <br>
이 두 가지 도구를 잘 이해하고 활용하면, 개발 생산성과 협업 효율성을 크게 높일 수 있습니다.
