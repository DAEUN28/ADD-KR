---
description: 블록 객체를 사용해 뷰를 애니메이팅하기 위한 옵션
---

# UIView.AnimationOptions

## Info
> **Type**: `Structure`
>
> **최근 수정일**: `2021-03-20`
>
> [원문 링크](https://developer.apple.com/documentation/uikit/uiview/animationoptions)

**Availability**

- iOS 4.0+
- Mac Catalyst 13.0+
- tvOS 9.0+

**Framework**

- UIKit

---

## Declaration

```swift
struct AnimationOptions
```

## Topics

---

### Initializers

- [`init(rawValue: UInt)`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1625037-init)

---

### Constants

- [`static var layoutSubviews: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622543-layoutsubviews)

  커밋할 때, (commit time) 서브뷰를 배치하여 부모와 함께 애니메이션되도록 합니다.

- [`static var allowUserInteraction: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622440-allowuserinteraction)

  뷰가 애니메이팅될 떄, 해당 뷰에 대한 유저 인터랙션을 허용합니다.

- [`static var beginFromCurrentState: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622575-beginfromcurrentstate)

  이미 진행 중인 애니메이션과 관련된 현재 설정에서 애니메이션을 시작합니다.

- [`static var `repeat`: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622487-repeat)

  애니메이션을 무기한 반복합니다.

- [`static var autoreverse: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622639-autoreverse)

  애니메이션을 실행했다가 원상태로 되돌립니다.(repeat옵션과 함께 사용)

- [`static var overrideInheritedDuration: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622434-overrideinheritedduration)

  애니메이션이 제출될 때, 지정된 기존 duration 값을 사용하도록 애니메이션을 강제합니다. 

- [`static var overrideInheritedCurve: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622514-overrideinheritedcurve)

  애니메이션이 제출될 때, 지정된 기존 curve 값을 사용하도록 애니메이션을 강제합니다.

- [`static var allowAnimatedContent: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622470-allowanimatedcontent)

  프로퍼티 값을 동적으로 변경하고, 뷰를 다시 그려서 뷰를 애니메이션합니다.

- [`static var showHideTransitionViews: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622462-showhidetransitionviews)

  뷰가 트랜지션될 때, 뷰를 숨기거나 표시합니다.

- [`static var overrideInheritedOptions: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622645-overrideinheritedoptions)

  애니메이션 타입 또는 옵션을 상속하지 않는 옵션

- [`static var curveEaseInOut: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622604-curveeaseinout)

  애니메이션이 느리게 시작되고, duration 동안 가속된 다음, 완료되기 전에 다시 느리게하는 ease-in ease-out curve를 지정합니다.

- [`static var curveEaseIn: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622495-curveeasein)

  ease-in curve는 애니메이션을 천천히 시작한 다음, 다음 진행에 따라 속도를 높입니다.

- [`static var curveEaseOut: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622656-curveeaseout)

  ease-out curve는 애니메이션을 빠르게 시작한 다음, 완료됨에 따라 느려집니다.

- [`static var curveLinear: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622478-curvelinear)

  linear 애니메이션 curve는 애니메이션이 duration 동안 균등하게 발생하도록 합니다.

- [`static var transitionFlipFromLeft: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622646-transitionflipfromleft)

  수직축을 중심으로 뷰를 왼쪽에서 오른쪽으로 뒤집는 트랜지션(뷰의 왼쪽은 앞으로, 오른쪽은 뒤로 이동)

- [`static var transitionFlipFromRight: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622573-transitionflipfromright)

  수직축을 중심으로 뷰를 오른쪽에서 왼쪽으로 뒤집는 트랜지션(뷰의 오른쪽은 앞으로, 왼쪽은 뒤로 이동)

- [`static var transitionCurlUp: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622637-transitioncurlup)

  뷰를 아래쪽에서 위로 컬링하는 트랜지션

- [`static var transitionCurlDown: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622455-transitioncurldown)

  뷰를 위쪽에서 아래로 컬링하는 트랜지션

- [`static var transitionCrossDissolve: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622499-transitioncrossdissolve)

  다음 뷰로 디졸브되는 트랜지션

- [`static var transitionFlipFromTop: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622548-transitionflipfromtop)

  수평축을 중심으로 뷰를 위에서 아래로 뒤집는 트랜지션(뷰의 윗면이 앞으로, 아랫면이 뒤로 이동)

- [`static var transitionFlipFromBottom: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/1622632-transitionflipfrombottom)

  수평축을 중심으로 뷰를 아래에서 위로 뒤집는 트랜지션(뷰의 아랫면이 앞으로, 윗면이 뒤로 이동)

- [`static var preferredFramesPerSecond30: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/2806817-preferredframespersecond30)

  초당 30 프레임의 프레임 속도

- [`static var preferredFramesPerSecond60: UIView.AnimationOptions`](https://developer.apple.com/documentation/uikit/uiview/animationoptions/2806816-preferredframespersecond60)

  초당 60 프레임의 프레임 속도

## Relationships

---

### Conforms To

- [`OptionSet`](https://developer.apple.com/documentation/swift/optionset)

