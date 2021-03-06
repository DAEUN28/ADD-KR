---
description: 특정 시간 간격이 경과한 후 실행되어 지정된 메시지를 target 객체로 보내는 타이머
---

# Timer

## Info
> **Type**: `Class`
>
> **최근 수정일**: `2021-03-06`
>
> [원문 링크](https://developer.apple.com/documentation/foundation/timer)

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

``` swift
class Timer : NSObject
```

## Overview

타이머는 런 루프와 함께 작동합니다. 런 루프는 타이머에 강한 참조를 유지하므로 런 루프에 타이머를 추가한 후 타이머에 강한 참조를 유지할 필요가 없습니다.

타이머를 효과적으로 사용하려면 런 루프가 작동하는 방식에 대해 알아야 합니다. 자세한 내용은 [Threading Programming Guide](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/Multithreading/Introduction/Introduction.html#//apple_ref/doc/uid/10000057ii) 을 참고하세요.

타이머는 실시간 메커니즘이 아닙니다. 긴 런 루프 호출 중에 또는 런 루프가 타이머를 모니터링하지 않는 모드에 있는 동안 타이머가 작동되는 경우, 런 루프가 타이머를 확인할 다음 시간까지 타이머가 작동되지 않습니다. 따라서 타이머가 작동하는 실제 시간을 상당히 느릴 수 있습니다. [Timer Tolerance](https://developer.apple.com/documentation/foundation/timer#1667624)를 참고하세요.

타이머는 Core Foundation의 [CFRunLoopTimer](https://developer.apple.com/documentation/corefoundation/cfrunlooptimer)와 toll-free bridging할 수 있다. 자세한 내용은 [Toll-Free Bridging](https://developer.apple.com/library/archive/documentation/General/Conceptual/CocoaEncyclopedia/Toll-FreeBridgin/Toll-FreeBridgin.html#//apple_ref/doc/uid/TP40010810-CH2)을 참고하세요.

### 반복하는 타이머와 반복하지 않는 타이머의 비교

타이머 생성 시 반복 여부를 지정합니다. 반복되지 않는 타이머는 한 번 작동한 후 자동으로 무효화되므로 타이머가 다시 작동되지 않습니다. 반면, 반복하는 타이머는 작동한 다음 동일한 런 루프에서 다시 스케줄됩니다. 반복하는 타이머는 항상 실제 작동 시간이 아닌 스케줄된 시간에 따라 스케줄합니다. 예를 들어, 타이머가 특정 시간 이후 5초마다 작동되도록 스케줄된 경우, 실제 작동 시간보다 지연되더라도 스케줄된 작동 시간은 항상 5초 간격을 보장합니다. 작동 시간이 너무 지연되어 스케줄된 시간중 하나 이상 경과하면 타이머는 해당 기간 동안 한 번만 작동되며, 작동 후 타이머는 다음 작동 시간으로 스케줄된 시간으로 다시 스케줄됩니다.

### 타이머의 허용 오차

iOS 7과 그 이후 버전, macOS 10.9와 그 이후 버전에서 타이머의 허용 오차([tolerance](https://developer.apple.com/documentation/foundation/timer/1415085-tolerance))를 지정할 수 있습니다. 이러한 유연성은 타이머 작동 시 시스템의 전력 절감 및 반응성을 최적화하는 능력을 향상시킵니다. 타이머는 스케줄된 작동 시간과 허용 오차 사이에 언제든지 작동될 수 있습니다. 타이머는 스케줄된 작동 시간 이전에 작동하지 않습니다. 반복하는 타이머의 경우, 드리프트를 피하기 위해 개별 실행 시간에 적용되는 허용 오차에 관계없이 다음 작동 시간을 원래 작동 시간으로부터 계산합니다. 기본 값은 0이며, 이는 허용 오차가 적용되지 않음을 의미합니다. 시스템은 [tolerance](https://developer.apple.com/documentation/foundation/timer/1415085-tolerance)의 값에 관계없이 특정 타이머에 작은 허용 오차를 적용할 수 있는 권한을 가집니다.

타이머의 사용자는 타이머에 대한 적절한 허용 오차를 결정할 수 있습니다. 일반적으로 반복하는 타이머의 허용오차는 적어도 시간 간격의 10%로 설정합니다. 허용 오차가 작더라도 앱의 전력 사용에 상당히 긍정적 효과를 미칩니다. 시스템은 허용오차에 대해 최대값을 적용할 수 있습니다.

### 런 루프에서의 타이머 스케줄링

타이머는 한 번에 하나의 런 루프에서만 등록할 수 있지만, 해당 런 루프 내에서 여러 런 루프 모드에 추가할 수 있습니다. 다음은 타이머를 생성하는 세가지 방법입니다.

- 현재 런 루프의 default 모드에 타이머를 스케줄하고 생성하려면 [`scheduledTimer(timeInterval:invocation:repeats:)`](https://developer.apple.com/documentation/foundation/timer/1415941-scheduledtimer) 또는 [`scheduledTimer(timeInterval:target:selector:userInfo:repeats:)`](https://developer.apple.com/documentation/foundation/timer/1412416-scheduledtimer) 클래스 메서드를 사용하세요.
- 런 루프에 스케줄링하지 않고 타이머 객체를 생성하려면 [`init(timeInterval:invocation:repeats:)`](https://developer.apple.com/documentation/foundation/timer/1407170-init) 또는 [`init(timeInterval:target:selector:userInfo:repeats:)`](https://developer.apple.com/documentation/foundation/timer/1408356-init) 클래스 메서드를 사용하세요.(생성 후에 반드시 해당하는 런 루프 객체의  [`add(_:forMode:)`](https://developer.apple.com/documentation/foundation/runloop/1418468-add) 메서드를 호출해 런 루프에 타이머를 추가해야 합니다.)
- 타이머를 할당하고 초기화하려면  [`init(fireAt:interval:target:selector:userInfo:repeats:)`](https://developer.apple.com/documentation/foundation/timer/1415700-init) 메서드를 사용하세요.(생성 후에 반드시 해당하는 런 루프 객체의  [`add(_:forMode:)`](https://developer.apple.com/documentation/foundation/runloop/1418468-add) 메서드를 호출해 런 루프에 타이머를 추가해야 합니다.)

한 번 런 루프에 스케줄된 타이머는 무효화 되기 전까지 특정 간격에 작동됩니다. 반복하지 않는 타이머는 작동 후 즉시 무효화됩니다. 그러나 반복하는 타이머의 경우 반드시 [`invalidate()`](https://developer.apple.com/documentation/foundation/timer/1415405-invalidate) 메서드를 호출하여 타이머 객체를 무효화해야 합니다. 이 메서드를 호출하면 현재 런 루프에서 타이머를 제거할 것을 요청합니다. 따라서 항상 타이머를 install한 스레드와 같은 스레드에서 [`invalidate()`](https://developer.apple.com/documentation/foundation/timer/1415405-invalidate) 메서드를 호출해야 합니다. 타이머를 무효화하면 더 이상 런 루프에 영향을 미치지 않도록 타이머가 즉시 비활성화됩니다. 그런 다음 [`invalidate()`](https://developer.apple.com/documentation/foundation/timer/1415405-invalidate) 메서드가 반환되기 직전 또는 이후에 런 루프에서 타이머(및 타이머에 대한 강한 참조)가 제거됩니다. 무효화된 타이머 객체는 재사용할 수 없습니다.

반복하는 타이머가 작동된 후, 지정된 [tolerance](https://developer.apple.com/documentation/foundation/timer/1415085-tolerance) 내에서 마지막으로 스케줄된 작동 시간 이후 타이머의 시간 간격의 정수 배수에 가장 가까운 미래 시간에 대한 다음 작동을 스케줄합니다. 셀렉터 또는 invocation을 작동하는데 걸리는 시간이 지정된 간격보다 긴 경우, 타이머는 다음 작동만 스케줄합니다. 즉, 타이머는 지정된 셀렉터 또는 invocation을 호출하는 동안 어떠한 누락이 발생하는 것에 대해 책임지지 않습니다.

### Subclassing Notes

Timer를 상속하지 마세요.

## Topics

---

### 타이머 생성

- [`class func scheduledTimer(withTimeInterval: TimeInterval, repeats: Bool, block: (Timer) -> Void) -> Timer`](https://developer.apple.com/documentation/foundation/timer/2091889-scheduledtimer)

  타이머를 생성한 후 현재 런 루프의 default 모드에 스케줄합니다.

- [`class func scheduledTimer(timeInterval: TimeInterval, target: Any, selector: Selector, userInfo: Any?, repeats: Bool) -> Timer`](https://developer.apple.com/documentation/foundation/timer/1412416-scheduledtimer)

  타이머를 생성한 후 현재 런 루프의 default 모드에 스케줄합니다.

- [`class func scheduledTimer(timeInterval: TimeInterval, invocation: NSInvocation, repeats: Bool) -> Timer`](https://developer.apple.com/documentation/foundation/timer/1415941-scheduledtimer)

  새로운 타이머를 생성한 후 현재 런 루프의 default 모드에 스케줄합니다.

- [`init(timeInterval: TimeInterval, repeats: Bool, block: (Timer) -> Void)`](https://developer.apple.com/documentation/foundation/timer/2091888-init)

  시간 간격과 block으로 타이머 객체를 초기화합니다.

- [`init(timeInterval: TimeInterval, target: Any, selector: Selector, userInfo: Any?, repeats: Bool)`](https://developer.apple.com/documentation/foundation/timer/1408356-init)

  객체와 셀렉터로 타이머 객체를 초기화합니다.

- [`init(timeInterval: TimeInterval, invocation: NSInvocation, repeats: Bool)`](https://developer.apple.com/documentation/foundation/timer/1407170-init)

  invocation 객체로 타이머 객체를 초기화합니다.

- [`init(fire: Date, interval: TimeInterval, repeats: Bool, block: (Timer) -> Void)`](https://developer.apple.com/documentation/foundation/timer/2091887-init)

  날짜와 시간 간격, block으로 타이머 객체를 초기화합니다.

- [`init(fireAt: Date, interval: TimeInterval, target: Any, selector: Selector, userInfo: Any?, repeats: Bool)`](https://developer.apple.com/documentation/foundation/timer/1415700-init)

  객체와 셀렉터로 타이머 객체를 초기화합니다.

---

### 타이머 실행

- [`func fire()`](https://developer.apple.com/documentation/foundation/timer/1414035-fire)

  타이머의 메시지를 taget으로 보냅니다.

---

### 타이머 정지

- [`func invalidate()`](https://developer.apple.com/documentation/foundation/timer/1415405-invalidate)

  Stops the timer from ever firing again and requests its removal from its run loop.

  타이머를 다시 실행하지 않도록 멈추고 런 루프에서 제거를 요청합니다.

---

### 타이머 정보 검색

- [`var isValid: Bool`](https://developer.apple.com/documentation/foundation/timer/1408249-isvalid)

  타이머의 유효 여부를 나타내는 불 값

- [`var fireDate: Date`](https://developer.apple.com/documentation/foundation/timer/1407353-firedate)

  타이머가 작동되는 날짜

- [`var timeInterval: TimeInterval`](https://developer.apple.com/documentation/foundation/timer/1409024-timeinterval)

  타이머의 시간 간격(초)

- [`var userInfo: Any?`](https://developer.apple.com/documentation/foundation/timer/1408911-userinfo)

  userInfo 객체의 리시버

---

### 허용 오차 설정

- [`var tolerance: TimeInterval`](https://developer.apple.com/documentation/foundation/timer/1415085-tolerance)

  타이머가 작동될 수 있는 스케줄된 작동 날짜 이후의 시간

---

### Combine Publisher로 메시지 실행

- [`static func publish(every: TimeInterval, tolerance: TimeInterval?, on: RunLoop, in: RunLoop.Mode, options: RunLoop.SchedulerOptions?) -> Timer.TimerPublisher`](https://developer.apple.com/documentation/foundation/timer/3329589-publish)

  지정된 간격에 따라 현재 날짜를 반복적으로 방출하는 publisher를 반환합니다.

- [`class Timer.TimerPublisher`](https://developer.apple.com/documentation/foundation/timer/timerpublisher)

  지정된 간격으로 현재 날짜를 반복적으로 방출하는 publisher

## Relationships

---

### Inherits From

- [`NSObject`](https://developer.apple.com/documentation/objectivec/nsobject)
