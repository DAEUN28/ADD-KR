---
description: host 운영 체제 및 기타 프로세스와 앱의 상호작용을 관리하고 낮은 수준의 동시성 기능을 구현합니다.
---

# Processes and Threads

## Info
> **Type**: `Collection`
>
> **최근 수정일**: `2021-01-04`
>
> [원문 링크](https://developer.apple.com/documentation/foundation/processes_and_threads)

**Framework**

- Foundation

## Topics

### 런루프 스케줄링

- class RunLoop

  input source를 관리하는 객체에 대한 인터페이스

- [class Timer](Task Management/Timer/README.md)

  특정 시간 간격이 경과한 후 실행되어 지정된 메시지를 target 객체로 보내는 타이머

---

### 프로세스 정보

- class ProcessInfo

  현재 프로세스에 대한 정보 모음

---

### 스레드와 Locking

- class Thread

  실행 스레드

- protocol NSLocking

  lock 객체를 정의하는 클래스가 채택한 기본적인 메서드들

- class NSLock

  같은 앱의 여러 실행 스레드의 작업을 조정하는 객체

- class NSRecursiveLock

  교착상태 없이 같은 스레드에서 여러 번 획득할 수 있는 lock

- class NSDistributedLock

  여러 호스트의 여러 앱이 파일과 같은 일부 공유 리소스에 대한 접근을 제한하는데 사용할 수 있는 lock

- class NSConditionLock

  특정 사용자 정의 조건과 연결할 수 있는 lock

- class NSCondition

  POSIX-style 조건에 사용되는 의미론을 따르는 조건 변수

---

### Operations

- class OperationQueue

  작업 실행을 제어하는 큐

- class Operation

  단일 작업과 연관된 코드 및 데이터를 나타내는 추상 클래스

- class BlockOperation

  하나 이상의 블록의 동시 실행을 관리하는 작업

---

### 스크립트와 외부 작업

- class Process

  현재 프로세스의 하위 프로세스를 나타내는 객체

- class NSUserScriptTask

  스크립트를 실행하는 객체

- class NSUserAppleScriptTask

  AppleScript 스크립트를 실행하는 객체

- class NSUserAutomatorTask

  Automator 워크플로우를 실행하는 객체

- class NSUserUnixTask

  unix 앱을 실행하는 객체

## See Also

---

### Low-Level Utilities

- XPC

  안전한 프로세스 간 통신을 관리합니다.

- Object Runtime

  기본 Objective-C 기능, 코코아 디자인 패턴 및 Swift 통합에 대한 low-level의 지원을 받을 수 있습니다.

- Streams, Sockets, and Ports

  low-level Unix 기능을 사용하여 파일, 프로세스 및 넽워크 간의 입력 및 출력을 관리합니다. 