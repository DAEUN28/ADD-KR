---
description: 애플 실리콘이 있는 맥용 소프트웨어를 만드는데 필요한 리소스를 확보하세요.
---

# Apple Silicon

## Info
> **Type**: `Collection`
>
> **최근 수정일**: `2020-12-23`
>
> [원문 링크](https://developer.apple.com/documentation/apple_silicon)

---

## Overview

애플 실리콘에서 네이티브하게 작동하는 앱, 프레임워크, 플러그인 그리고 다른 실행 파일을 구축하세요. 애플 프레임워크 및 기술에 기반하여 실행파일을 구축할 때 중요한 단계는 arm64 아키텍처를 위해 코드를 다시 컴파일하는 것입니다. 하드웨어별 세부 정보를 사용하거나 low-level의 기능이 필요할 경우 애플 실리콘을 지원하기 위해 필요에 따라 코드를 수정하세요. 

![Figure1](Resource/appleSilicon-figure1.png)

최상의 성능을 위해 애플 실리콘은 가끔 하드웨어 리소스 사용 방식을 조정합니다. 가능한 higer-level 기술을 사용해 하드웨어에 대한 의존성을 최소화하세요. 예시로, 직접 스레드를 생성, 관리하는 대신 Grand Central Dispath를 사용하세요. 애플 실리콘에서 변경 사항을 테스트하여 수정한 코드가 최적으로 작동하는지 확인해보세요.



## Topics

---

### 필수

- Porting Your macOS Apps to Apple Silicon

  애플 실리콘과 인텔 기반 맥 컴퓨터 모두에서 동작할 수 있는 버전의 맥앱을 만듭니다.

- Building a Universal macOS Bunary

  애플 실리콘과 인텔 기반 맥 컴퓨터 모두에서 네이티브하게 동작할 수 있는 맥 앱 및 다른 실행가능한 코드를 만듭니다.

---

### 일반적인 이식 팁

- Addressing Architectural Differences in Your macOS Code

  애플 실리콘과 인텔 기반 맥 컴퓨터 간의 아키텍처 차이에서 발생하는 문제를 해결합니다ㅣ.

- Porting Your Audio Code to Apple Silicon

  애플 실리콘 맥 컴퓨터에서 실행할 때 발생하는 특정 오디오 코드의 이슈를 제거합니다.

- Porting Just-In-Time Compilers to Apple Silicon

  강화된 런타임 기능과 애플 실리콘에서 동작하도록 just-in-time(JIT) 컴파일러를 수정합니다.

---

### 그래픽

- Porting Your Metal Code to Apple Silicon

  애플 실리콘과 인텔 기반 맥 컴퓨터 모두에서 동작하는 메탈 앱의 버전을 만듭니다.

---

### 성능

- Turning Your Code's Performance for Apple Silicon

  애플 실리콘과 인텔 기반 맥 컴퓨터 모두에서 최상의 성능을 얻기 위해 코드를 개선합니다.

---

### Rosetta

- About the Rosetta Translation Environment

  어떻게 로제타가 실행 파일을 변환하는지 학습하고, 로제타가 변환할 수 없는 것은 무엇인지 이해합니다.

---

### 맥에서의 iOS 앱

- Running Your iOS Apps on macOS

  애플 실리콘 기반 맥에서 수정 없이 iOS 앱을 실행합니다. 하지만 macOS에서 앱이 실행될 수 없는 경우에는 제외됩니다.

---

### 커널 및 드라이버

- Implementing Drivers, System Extensions, and Kexts

  하드웨어와 통신하고 low-level 서비스를 제공하기 위해 몇 가지 작업에만 커널 익스텐션을 사용하여 드라이버 및 시스템 익스텐션을 생성합니다.

- Installing a Custom Kernel Extension

  custom installer package를 사용해 커널 익스텐션을 설치하고, 사용자가 설치 프로세스를 이해할 수 있도록 돕습니다.

- Debugging a Custom Kernel Extension

  두번째 맥에서 커스텀 커널 익스텐션을 디버깅할 수 있도록 시스템을 구성합니다.
