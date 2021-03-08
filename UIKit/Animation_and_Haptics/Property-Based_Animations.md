---
description: 뷰의 속성을 변경하여 애니메이션을 생성하세요.
---

# Property-Based Animations

## Info

> **Type**: `Collection`
>
> **최근 수정일**: `2021-03-07`
>
> [원문 링크](https://developer.apple.com/documentation/uikit/animation_and_haptics/property-based_animations)

**Framework**

- UIKit

---

## Topics

### First Steps

---

- [`class UIViewPropertyAnimator`](UIViewPropertyAnimator.md)

  뷰 변경 사항을 애니메이션화하고 해당 애니메이션의 동적 수정을 허용하는 클래스

- [`protocol UIViewAnimating`](https://developer.apple.com/documentation/uikit/uiviewanimating)

  커스텀 애니메이터 객체를 구현하기위한 인터페이스

### 타이밍 곡선

---

- [`protocol UITimingCurveProvider`](https://developer.apple.com/documentation/uikit/uitimingcurveprovider)

  애니메이션을 수행하는데 필요한 타이밍 정보를 제공하는 인터페이스

- [`class UISpringTimingParameters`](https://developer.apple.com/documentation/uikit/uispringtimingparameters)

  spring 동작을 모방한 애니메이션에 대한 타이밍 정보

- [`class UICubicTimingParameters`](https://developer.apple.com/documentation/uikit/uicubictimingparameters)

  ubic Bézier 곡선 형태 애니메이션에 대한 타이밍 정보

### 진행 중인 애니메이션

---

- [`protocol UIViewImplicitlyAnimating`](https://developer.apple.com/documentation/uikit/uiviewimplicitlyanimating)

  애니메이션이 실행되는 동안 수정하기 위한 인터페이스

## See Also

### 컨텐츠 애니메이션

- [View Controller Transitions](https://developer.apple.com/documentation/uikit/animation_and_haptics/view_controller_transitions)

  뷰컨트롤러에서 다른 뷰컨트롤러로의 커스텀 트랜지션을 정의하세요.

