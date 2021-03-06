---
description: input source를 관리하는 객체의 인터페이스
---

# RunLoop

## Info
> **Type**: `Class`
>
> **최근 수정일**: `2021-03-06`
>
> [원문 링크](https://developer.apple.com/documentation/foundation/runloop)

**Availability**

- iOS 2.0+
- macOS 10.0+
- Mac Catalyst 13.0+
- tvOS 9.0+
- watchOS 2.0+

**Framework**

- Foundation

---

## Declaration

```swift
class RunLoop: NSObject
```

## Overview

RunLoop 객체는 window 시스템, [Port](https://developer.apple.com/documentation/foundation/port) 객체 및 [NSConnection]() 객체의 마우스 및 키보드 이벤트 같은 소스에 대한 입력을 처리합니다. 또한 RunLoop객체는 [Timer](App-Frameworks/Foundation/Task-Management/Timer/README.md) 이벤트를 처리합니다.

앱이 RunLoop 객체를 생성하거나 명시적으로 관리하지 않습니다. 앱의 메인 스레드를 포함한 각 [Thread](https://developer.apple.com/documentation/foundation/thread) 객체는 필요에 따라 자동으로 생성된 RunLoop 객체를 가집니다. 만약 현재 스레드의 런루프에 접근해야 하는 경우 [current](https://developer.apple.com/documentation/foundation/runloop/1412291-current) 클래스 메서드를 사용할 수 있습니다.

RunLoop의 관점에서 보면, [Timer](App-Frameworks/Foundation/Task-Management/Timer/README.md) 객체는 "입력"이 아닙니다. 타이머는 특별한 타입이며, 즉, 타이머가 작동할 때 런루프의 복귀를 유발하지 않는다는 것을 뜻합니다.

> **Warning**
>
> RunLoop 클래스는 일반적으로 스레드가 안전하다고 간주되지 않으며, RunLoop의 메서드들은 현재 스레드의 컨텍스트에서만 호출되어야 합니다. 다른 스레드에서 실행되는 RunLoop 객체의 메서드를 호출해서는 안됩니다. 호출한다면 예기치 않은 결과가 발생할 수 있습니다.

## Topics

---

### 런루프와 모드 접근

- [`class var current: RunLoop`](https://developer.apple.com/documentation/foundation/runloop/1412291-current)

  현재 스레드의 런루프를 반환합니다.

- [`var currentMode: RunLoop.Mode?`](https://developer.apple.com/documentation/foundation/runloop/1412652-currentmode)

  리시버의 현재 입력 모드

- [`func limitDate(forMode: RunLoop.Mode) -> Date?`](https://developer.apple.com/documentation/foundation/runloop/1412837-limitdate)

  지정된 모드에서 런루프를 한 번 돈 후 다음 타이머가 실행되도록 스케줄된 날짜를 반환합니다.

- [`class var main: RunLoop`](https://developer.apple.com/documentation/foundation/runloop/1418388-main)

  현재 스레드의 런루프를 반환합니다.

- [`func getCFRunLoop() -> CFRunLoop`](https://developer.apple.com/documentation/foundation/runloop/1410140-getcfrunloop)

  리시버의 기본 CFRunLoop 객체를 반환합니다.

- [`struct RunLoop.Mode`](https://developer.apple.com/documentation/foundation/runloop/mode)

---

### 타이머 관리

- [`func add(Timer, forMode: RunLoop.Mode)`](https://developer.apple.com/documentation/foundation/runloop/1418468-add)

  지정된 타이머를 지정된 입력 모드로 등록합니다.

---

### 포트 관리

- [`func add(Port, forMode: RunLoop.Mode)`](https://developer.apple.com/documentation/foundation/runloop/1417637-add)

  지정된 런루프의 모드에 포트를 입력 소스로 추가합니다.

- [`func remove(Port, forMode: RunLoop.Mode)`](https://developer.apple.com/documentation/foundation/runloop/1414332-remove)

  지정된 런루프의 입력 모드에서 포트를 삭제합니다.

---

### 루프 실행

- [`func run()`](https://developer.apple.com/documentation/foundation/runloop/1412430-run)

  리시버를 영구적인 루프에 넣고, 연결된 모든 입력 소스의 데이터를 처리합니다.

- [`func run(mode: RunLoop.Mode, before: Date) -> Bool`](https://developer.apple.com/documentation/foundation/runloop/1411525-run)

  루프를 한번 실행하여, 지정된 날짜까지 지정된 모드의 입력을 차단합니다.

- [`func run(until: Date)`](https://developer.apple.com/documentation/foundation/runloop/1415778-run)

  지정된 날짜까지 루프를 실행하는 동안 연결된 모든 입력 소스의 데이터를 처리합니다.

- [`func acceptInput(forMode: RunLoop.Mode, before: Date)`](https://developer.apple.com/documentation/foundation/runloop/1417143-acceptinput)

  한번 또는 지정된 날짜까지 루프를 실행하여 지정된 모드의 입력만 받습니다.

---

### 메세지 스케줄링 및 취소

- [`func perform(Selector, target: Any, argument: Any?, order: Int, modes: [RunLoop.Mode])`](https://developer.apple.com/documentation/foundation/runloop/1409310-perform)

  리시버에 대한 메시지 전송을 예약합니다.

- [`func cancelPerform(Selector, target: Any, argument: Any?)`](https://developer.apple.com/documentation/foundation/runloop/1418077-cancelperform)

  이전에 예약된 메시지 전송을 취소합니다.

- [`func cancelPerformSelectors(withTarget: Any)`](https://developer.apple.com/documentation/foundation/runloop/1414208-cancelperformselectors)

  지정된 타겟에 아직 전달되지 않았고, 실행이 예약된 모든 명령을 취소합니다.

---

### Combine Publishers 스케줄링

- [`func schedule(options: RunLoop.SchedulerOptions?, () -> Void)`](https://developer.apple.com/documentation/foundation/runloop/3329474-schedule)

  스케줄러의 최소 허용오차를 사용해 지정된 날짜 이후 작업을 수행합니다.

- [`func schedule(after: RunLoop.SchedulerTimeType, tolerance: RunLoop.SchedulerTimeType.Stride, options: RunLoop.SchedulerOptions?, () -> Void)`](https://developer.apple.com/documentation/foundation/runloop/3329473-schedule)

  지정된 허용오차와 옵션을 사용해 지정된 날짜 이후 작업을 수행합니다.

- [`func schedule(after: RunLoop.SchedulerTimeType, interval: RunLoop.SchedulerTimeType.Stride, tolerance: RunLoop.SchedulerTimeType.Stride, options: RunLoop.SchedulerOptions?, () -> Void) -> Cancellable`](https://developer.apple.com/documentation/foundation/runloop/3329472-schedule)

  지정된 허용오차와 옵션을 사용해 지정된 날짜 이후 지정된 빈도에 작업을 수행합니다.

- [`var minimumTolerance: RunLoop.SchedulerTimeType.Stride`](https://developer.apple.com/documentation/foundation/runloop/3329470-minimumtolerance)

  런루프 스케줄러가 허용하는 최소 허용오차

- [`var now: RunLoop.SchedulerTimeType`](https://developer.apple.com/documentation/foundation/runloop/3329471-now)

  현재 시간에 대한 런루프 스케줄러의 정의

- [`struct RunLoop.SchedulerTimeType`](https://developer.apple.com/documentation/foundation/runloop/schedulertimetype)

  런루프가 사용하는 스케줄러 시간 타입

- [`struct RunLoop.SchedulerOptions`](https://developer.apple.com/documentation/foundation/runloop/scheduleroptions)

  런루프 스케줄러 작동에 영향을 미치는 옵션 집합

---

### 상수

- [Run Loop Modes](https://developer.apple.com/documentation/foundation/runloop/run_loop_modes)

  NSRunLoop는 다음과 같은 런루프 모드를 정의합니다.

---

### 인스턴스 메서드

- [`func perform(() -> Void)`](https://developer.apple.com/documentation/foundation/runloop/2091881-perform)
- [`func perform(inModes: [RunLoop.Mode], block: () -> Void)`](https://developer.apple.com/documentation/foundation/runloop/2091880-perform)

## Relationships

---

### Inherits From

- [`NSObject`](https://developer.apple.com/documentation/objectivec/nsobject)

---

### Conforms To

- [`Scheduler`](https://developer.apple.com/documentation/combine/scheduler)

## See Also

---

### 런루프 스케줄링

- [`class Timer`](App-Frameworks/Foundation/Task-Management/Timer/README.md)

  특정 시간 간격이 경과한 후 실행되어 지정된 메시지를 target 객체로 보내는 타이머