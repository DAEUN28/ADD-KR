---
description: 뷰 변경 사항을 애니메이션화하고 해당 애니메이션의 동적 수정을 허용하는 클래스
---

# UIViewPropertyAnimator

## Info
> **Type**: `Class`
>
> **최근 수정일**: `2021-02-20`
>
> [원문 링크](https://developer.apple.com/documentation/uikit/uiviewpropertyanimator)

**Availability**

- iOS 10.0+
- Mac Catalyst 13.0+
- tvOS 10.0+

**Framework**

- UIKit

---

## Declaration

```swift
class UIViewPropertyAnimator : NSObject
```

## Overview

UIViewPropertyAnimator 객체를 사용하면 뷰 변경 사항을 애니메이션화할 수 있고, 애니메이션이 완료되기 전에 애니메이션을 동적으로 수정할 수 있습니다. 프로퍼티 애니메이터를 사용하면, 애니메이션을 처음부터 끝까지 정상적으로 실행하거나 상호적인(interactive) 애니메이션으로 전환하고 직접 타이밍을 제어할 수 있습니다. animator는 frame, center, alpha 그리고 transform과 같은 뷰의 animatable 프로퍼티에서 작동하여, 사용자가 제공한 블록에서 필요한 애니메이션을 만듭니다.

프로퍼티 애니메이터 객체를 생성할 때는, 다음을 지정합니다:

- 하나 이상의 뷰 프로퍼티를 수정하는 코드를 포함한 블록
- 실행 과정에서 애니메이션 속도를 정의하는 타이밍 커브
- 애니메이션의 지속 시간(초단위)
- 애니메이션이 완료될 때 실행할 옵셔널 completion block

애니메이션 블록에서, animatable 프로퍼티의 값을 해당 뷰에 반영할 최종 값으로 설정합니다. 예를 들어 뷰를 fade out하려면, 블록에서 alpha 프로퍼티를 0으로 설정합니다. 프로퍼티 애니메이터 객체는 해당 프로퍼티의 값을 초기값에서 블록에서 지정한 새로운 값으로 조장하는 애니메이션을 생성합니다.

프로퍼티 값이 변경되는 속도는 프로퍼티 애니메이터를 생성할 때 지정한 타이밍 커브에 의해 제어됩니다. 프로퍼티 애니메이터는 linear, ease-in 그리고 ease-out과 같은 빌트인 UIKit 애니메이션 커브를 지원합니다. 또한 cubic Bezier curve 또는 spring 함수를 사용해 애니메이션 타이밍을 제어할 수 있습니다.

표준 이니셜라이저 중 하나를 사용해 애니메이터를 생성할 경우, 애니메이션을 명시적으로 시작하기 위해 startAnimation() 메서드를 호출해야 합니다. 만약 애니메이터 생성 직후 애니메이션을 시작하고 한다면, 표준 이니셜라이저 대신 runningPropertyAnimator(withDuration:delay:options:animatons:completion:) 메서드를 사용하세요.

이 클래스는 애니메이션 시작, 중지 및 수정을 위한 메서드를 정의하는 UIViewanimating과 UIViewImplictlyAnimating 프로토콜을 채택합니다. 이 프로토콜들의 메서드에 대한 더 자세한 내용은 UIViewAnimating과 UIViewImplictlyAnimating에서 확인하세요.

### 동적 애니메이션 수정

프로퍼티 애니메이터를 사용하면 애니메이션의 타이밍과 실행을 프로그래밍적으로 제어할 수 있습니다. 특히, 다음 작업을 할 수 있습니다:

- 시작, 일시중지, 재개 그리고 중지. UIViewAnimating 프로토콜의 메서드를 확인하세요.
- addAnimations(\_:)과 addAnimations(_:delayFactor:) 메서드를 사용해 기존 애니메이션 시작 후 애니메이션 블록을 추가합니다.
- fractionComplete 프로퍼티를 수정해 일시정지된 애니메이션을 건너뜁니다.(Scrub through)
- isReversed 프로퍼티를 사용해 애니메이션의 방향을 변경합니다.
- 애니메이션을 일시중지해 부분적으로 완료된 애니메이션의 타이밍 및 지속시간을 수정하고, continueAnimation(withTimingParameters:durationFactor:) 메서드를 사용해 완료합니다.

대부분의 기본동작은 이 클래스가 채택한 UIViewAnimating 프로토콜 프로퍼티에 의해 제어됩니다. 이러한 메서드와 프로퍼티를 사용해 애니메이션을 시작, 일시중지, 재개 및 중지합니다. 또한 이 메서드와 프로퍼티를 사용해 애니메이션을 건너뛰고 방향을 변경할 수 있습니다. 이 클래스의 메서드와 프로퍼티를 사용해 애니메이션 블록 자체를 수정하고 타이밍 정보를 업데이트합니다.

## Topics

### 프로퍼티 애니메이터 초기화

---

- init(duration: TimeInterval, curve: UIView.AnimationCurve, animations: (() -> Void)?)

  빌트인 UIKit 타이밍 커브를 사용해 애니메이터를 초기화합니다.

- init(duration: TimeInterval, controlPoint1: CGPoint, controlPoint2: CGPoint, animations: (() -> Void)?)

  cubic Bézier 타이밍 커브를 사용해 애니메이터 객체를 초기화합니다.

- init(duration: TimeInterval, dampingRatio: CGFloat, animations: (() -> Void)?)

  spring 기반 타이밍 정보를 사용해 애니메이터 객체를 초기화합니다.

- init(duration: TimeInterval, timingParameters: UITimingCurveProvider)

  커스텀 타이밍 커브 객체를 사용해 애니메이터 객체를 초기화합니다.

- class func runningPropertyAnimator(withDuration: TimeInterval, delay: TimeInterval, options: UIView.AnimationOptions, animations: () -> Void, completion: ((UIViewAnimatingPosition) -> Void)?) -> Self

  애니메이션 실행을 즉시 시작하는 애니메이터 객체를 생성하고 반환합니다.

### 애니메이션 수정

---

- func addAnimations(() -> Void)

  애니메이터에 지정된 애니메이션 블록을 추가합니다.

- func addAnimations(() -> Void, delayFactor: CGFloat)

  지연과 함께 애니메이터에 지정된 애니메이션 블록을 추가합니다.

- func addCompletion((UIViewAnimatingPosition) -> Void)

  애니메이터에 지정된 애니메이션 블록을 추가합니다.

- func continueAnimation(withTimingParameters: UITimingCurveProvider?, durationFactor: CGFloat)

  일시정지된 애니메이션의 타이밍과 지속기간을 조정합니다.

### 애니메이션 파라미터에 접근

---

- var duration: TimeInterval

  메인 애니메이션의 총 지속 시간(초)

- var delay: TimeInterval

  애니메이션이 시작되기까지의 지연 시간(초)

- var timingParameters: UITimingCurveProvider?

  애니메이션의 타이밍 커브를 결정하는데 사용되는 정보

- var isInterruptible: Bool

  애니메이터가 중단 가능하고 일시중지 또는 중지될 수 있는지 여부를 나타내는 불린 값

- var isUserInteractionEnabled: Bool

  애니메이션이 실행되는 동안 뷰가 터치 이벤트를 받을 수 있는지 여부를 나타내는 불린 값

- var isManualHitTestingEnabled: Bool

  애니메이션이 진행 중일 때 앱이 hit-testing을 관리하는지 여부를 나타내는 불린 값

- var scrubsLinearly: Bool

  일시중지된 애니메이션이 선형으로 스크럽되는지 지정된 타이밍 정보를 사용하는지 나타내는 불린 값

- var pausesOnCompletion: Bool

  완료된 애니메이션이 활성 상태로 유지되는지 나타내는 불린 값

## Relationships

### Inherits From

---

- NSObject

### Conforms To

---

- NSCopying
- UIViewImplicitlyAnimating

## See Also

### First Steps

---

- protocol UIViewAnimating

  커스텀 애니메이터 객체를 구현하기 위한 인터페이스