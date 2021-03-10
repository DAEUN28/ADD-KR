---
description: 뷰컨트롤러에서 다른 뷰컨트롤러로의 커스텀 트랜지션을 정의하세요.
---

# View Controller Transitions

## Info

> **Type**: `Collection`
>
> **최근 수정일**: `2021-03-08`
>
> [원문 링크](https://developer.apple.com/documentation/uikit/animation_and_haptics/view_controller_transitions)

**Framework**

- UIKit

---

## Topics

---

### 애니메이션 델리게이트

- [`protocol UIViewControllerTransitioningDelegate`](https://developer.apple.com/documentation/uikit/uiviewcontrollertransitioningdelegate)

  뷰컨트롤러 간의 고정길이(fixed-length) 또는 인터랙티브 트랜지션을 관리하는데 사용되는 객체를 제공하는 메서드 집합

---

### Non-인터랙티브 트랜지션

- [`protocol UIViewControllerAnimatedTransitioning`](https://developer.apple.com/documentation/uikit/uiviewcontrolleranimatedtransitioning)

  커스텀 뷰컨트롤러 트랜지션에 대한 애니메이션을 구현하기 위한 메서드 집합

- [`protocol UIViewControllerContextTransitioning`](https://developer.apple.com/documentation/uikit/uiviewcontrollercontexttransitioning)

  뷰컨트롤러 간의 트랜지션 애니메이션에 대한 컨텍스트(contextual) 정보를 제공하는 메서드 집합

---

### 인터랙티브 트랜지션

- [`class UIPercentDrivenInteractiveTransition`](https://developer.apple.com/documentation/uikit/uipercentdriveninteractivetransition)

  한 뷰컨트롤러와 다른 뷰컨트롤러간의 인터랙티브 애니메이션을 구동(drive)하는 객체

- [`protocol UIViewControllerInteractiveTransitioning`](https://developer.apple.com/documentation/uikit/uiviewcontrollerinteractivetransitioning)

  navigation controller와 같은 객체가 뷰컨트롤러 트랜지션을 구동(drive)할 수 있도록 하는 메서드 집합

- [`protocol UIViewImplicitlyAnimating`](https://developer.apple.com/documentation/uikit/uiviewimplicitlyanimating)

  애니메이션이 실행되는 동안 수정하기 위한 인터페이스

---

### 트랜지션 코디네이터

- [`protocol UIViewControllerTransitionCoordinator`](https://developer.apple.com/documentation/uikit/uiviewcontrollertransitioncoordinator)

  뷰컨트롤러 트랜지션과 관련된 애니메이션에 대한 지원을 제공하는 메서드 집합

  [`protocol UIViewControllerTransitionCoordinatorContext`](https://developer.apple.com/documentation/uikit/uiviewcontrollertransitioncoordinatorcontext)

  진행 중인 뷰컨트롤러 트랜지션에 대한 정보를 제공하는 메서드 집합



## See Also

---

### 컨텐츠 애니메이션

- [Property-Based Animations](Property-Based_Animations.md)

  뷰의 속성을 변경하여 애니메이션을 생성하세요.