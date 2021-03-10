---
description: life-cycle 이벤트 및 앱의 UI scene을 관리하고, 앱이 실행되는 traits 및 환경에 대한 정보를 얻으세요.
---

# App and Environment

## Info
> **Type**: `Collection`
>
> **최근 수정일**: `2021-03-06`
>
> [원문 링크](https://developer.apple.com/documentation/uikit/app_and_environment)

**Framework**

- UIKit

---

## Overview

iOS 13 이상 버전에서, 사용자는 사용자 인터페이스의 여러 인스턴스를 동시에 만들고 관리할 수 있고, app switcher를 사용해 인스턴스 간의 전환이 가능합니다. iPad에서 사용자는 앱의 여러 인스턴스를 나란히 표시할 수도 있습니다. UI의 각 인스턴스는 다른 콘텐츠를 표시하거나, 다른 방식으로 동일한 콘텐츠를 표시합니다. 예를 들어, 사용자는  특정 날짜를 표시하는 캘린더 앱의 한 인스턴스와 한달 전체를 표시하는 다른 인스턴스를 나타낼 수 있습니다.

UIKit은 기기 설정, 인터페이스 설정 및 사용자 선호도의 조합을 반영한 trait collections을 사용해 현재 환경에 대한 세부 정보를 전달합니다. 예를 들어, traits를 사용해 현재 뷰 또는 뷰컨트롤러에 대해 다크모드가 활성화되어 있는지 감지합니다. 현재 환경을 기반으로 콘텐츠를 커스텀하려면 [UIView](https://developer.apple.com/documentation/uikit/uiview) 또는 [UIViewController](https://developer.apple.com/documentation/uikit/uiviewcontroller) 객체의 현재 trait collection을 참조하세요. trait 변경사항 알림을 받기 원할 때는 [UITraitEnvironment](https://developer.apple.com/documentation/uikit/uitraitenvironment) 프로토콜을 채택하세요.

## Topics

---

### 생명 주기

- [Managing Your App's Life Cycle](Managing_App_Life_Cycle.md)

  foreground이나 background에 있을 때 시스템 notification에 응답하고, 기타 중요한 시스템 관련 이벤트를 처리하세요.

- [Responding to the Launch of Your App](https://developer.apple.com/documentation/uikit/app_and_environment/responding_to_the_launch_of_your_app)

  앱의 데이터 구조를 초기화하고, 실행 준비 및 시스템의 launch-time 요청에 응답하세요.

- [`class UIApplication`](https://developer.apple.com/documentation/uikit/uiapplication)

  iOS에서 실행되는 앱 제어 및 조정의 가장 중요한 지점(centralized point)

- [`protocol UIApplicationDelegate`](https://developer.apple.com/documentation/uikit/uiapplicationdelegate)

  앱의 공유 동작(shared behavior)을 관리하기 위한 메서드 집합

- [Scenes](https://developer.apple.com/documentation/uikit/app_and_environment/scenes)

  여러 앱 UI 인스턴스를 동시에 관리하고, 리소스를 적절한 인스턴스로 분배하세요.

---

### 멀티태스킹

- [Multitasking on iPad](Multitasking_on_iPad.md)

  멀티태스킹 API를 구현해 앱을 iPadOS와 원활하게 통합하세요.

---

### 기기 환경

- [`class UIDevice`](https://developer.apple.com/documentation/uikit/uidevice)

  현재 기기를 나타냅니다.

- [`class UIStatusBarManager`](https://developer.apple.com/documentation/uikit/uistatusbarmanager)

  상태바의 구성을 설명하는 객체

---

### Adaptivity

- [Responding to Changing Display Modes on Apple TV](https://developer.apple.com/documentation/uikit/app_and_environment/responding_to_changing_display_modes_on_apple_tv)

  기기의 화면 영역 변경에 따라 이미지와 리소스를 동적으로 변경하세요.

- [`class UITraitCollection`](https://developer.apple.com/documentation/uikit/uitraitcollection)

  가로 및 세로 사이즈 클래스, 디스플레이 비율, 사용자 인터페이스 종류(pad, phone 등)와 같은 trait을 포함한 앱의 iOS 인터페이스 환경

- [`protocol UITraitEnvironment`](https://developer.apple.com/documentation/uikit/uitraitenvironment)

  앱에서 iOS 인터페이스 환경을 사용할 수 있도록하는 메서드 집합

- [`protocol UIAdaptivePresentationControllerDelegate`](https://developer.apple.com/documentation/uikit/uiadaptivepresentationcontrollerdelegate)

  Presentation controller와 함께 앱의 trait 변경에 응답하는 방법을 결정하는 메서드 집합

- [`protocol UIContentContainer`](https://developer.apple.com/documentation/uikit/uicontentcontainer)

  뷰 컨트롤러의 콘텐츠를 크기 및 trait 변경에 맞게 조정하는 메서드 집합 

---

### Guided Acess

- [`protocol UIGuidedAccessRestrictionDelegate`](https://developer.apple.com/documentation/uikit/uiguidedaccessrestrictiondelegate)

  iOS의 Guided Access 기능에 대한 사용자 지정 제한을 추가하는데 사용하는 메서드 집합

- [`static func guidedAccessRestrictionState(forIdentifier: String) -> UIAccessibility.GuidedAccessRestrictionState`](https://developer.apple.com/documentation/uikit/uiaccessibility/1621153-guidedaccessrestrictionstate)

  지정된 guided access 제한에 대한에 제한 상태를 반환합니다.

---

### 아키텍처

- [Updating Your App from 32-Bit to 64-Bit Architecture](https://developer.apple.com/documentation/uikit/app_and_environment/updating_your_app_from_32-bit_to_64-bit_architecture)

  운영체제 최신 버전을 지원하도록 조정해 앱이 예상대로 동작하는지 확인합니다.

- [`func UIApplicationMain(Int32, UnsafeMutablePointer?>, String?, String?) -> Int32`](https://developer.apple.com/documentation/uikit/1622933-uiapplicationmain)

  앱 객체 및 앱 델리게이트를 생성하고 이벤트 사이클을 설정합니다.

## See Also

---

### 앱 구조

- https://developer.apple.com/documentation/uikit/documents_data_and_pasteboard

  앱의 데이터를 구조화(organize)하고 클립보드에서 공유하세요.

- [Resource Management](https://developer.apple.com/documentation/uikit/resource_management)

  앱 인터페이스를 구현하는데 사용하는 이미지, strings, 스토리 보드 및 nib 파일을 관리합니다.

- [App Extensions](https://developer.apple.com/documentation/uikit/app_extensions)

  앱의 기본 기능을 시스템의 다른 부분으로 확장합니다.

- [Interprocess Communication]()

  사용자에게 활동 기반 서비스를 표시합니다.

- [Mac Catalyst](https://developer.apple.com/documentation/uikit/mac_catalyst)

  Mac 기기에서 사용자가 실행할 수 있는 버전의 iPad 앱을 만드세요.

