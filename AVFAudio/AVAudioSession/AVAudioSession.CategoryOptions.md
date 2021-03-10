---
description: 선택적으로 오디오 동작을 지정하는 상수
---

# AVAudioSession.CategoryOptions

## Info
> **Type**: `Structure`
>
> **최근 수정일**: `2021-03-10`
>
> [원문 링크](https://developer.apple.com/documentation/avfaudio/avaudiosession/categoryoptions)

**Availability**

- iOS 6.0+
- macOS 10.15+
- Mac Catalyst 13.0+
- tvOS 9.0+
- watchOS 7.0+

**Framework**

- AVFAudio

## Declaration

```swift
struct CategoryOptions
```

## Overview

각 옵션은 특정 오디오 세션 카테고리에만 유효합니다.

## Topics

---

### 오디오 세션 옵션

- [`static var mixWithOthers: AVAudioSession.CategoryOptions`](https://developer.apple.com/documentation/avfaudio/avaudiosession/categoryoptions/1616611-mixwithothers)

  이 세션의 오디오가 다른 오디오 앱의 활성 세션의 오디오와 혼합되는지 여부를 나타내는 옵션

- [`static var duckOthers: AVAudioSession.CategoryOptions`](https://developer.apple.com/documentation/avfaudio/avaudiosession/categoryoptions/1616618-duckothers)

  이 세션의 오디오가 재생되는 동안 다른 오디오의 볼륨을 줄이는 옵션

- [`static var interruptSpokenAudioAndMixWithOthers: AVAudioSession.CategoryOptions`](https://developer.apple.com/documentation/avfaudio/avaudiosession/categoryoptions/1616534-interruptspokenaudioandmixwithot)

  앱에서 오디오를 재생할 때 다른 세션의 오디오 콘텐츠를 일시 중지할지 여부를 결정하는 옵션

- [`static var allowBluetooth: AVAudioSession.CategoryOptions`](https://developer.apple.com/documentation/avfaudio/avaudiosession/categoryoptions/1616518-allowbluetooth)

  블루투스 핸즈프리 기기가 사용 가능한 입력 경로로 표시되는지 여부를 결정하는 옵션

- [`static var allowBluetoothA2DP: AVAudioSession.CategoryOptions`](https://developer.apple.com/documentation/avfaudio/avaudiosession/categoryoptions/1771735-allowbluetootha2dp)

  이 세션의 오디오를 A2DP(Advanced Audio Distribution Profile)을 지원하는 블루투스 기기로 스트리밍할 수 있는지 여부를 결정하는 옵션

- [`static var allowAirPlay: AVAudioSession.CategoryOptions`](https://developer.apple.com/documentation/avfaudio/avaudiosession/categoryoptions/1771736-allowairplay)

  이 세션에서 AirPlay 장치로 오디오를 스트리밍할 수 있는지 여부를 결정하는 옵션

- [`static var defaultToSpeaker: AVAudioSession.CategoryOptions`](https://developer.apple.com/documentation/avfaudio/avaudiosession/categoryoptions/1616462-defaulttospeaker)

  세션의 오디오가 리시버 대신 내장 스피커로 기본 설정되는지 여부를 결정하는 옵션

- [`static var overrideMutedMicrophoneInterruption: AVAudioSession.CategoryOptions`](https://developer.apple.com/documentation/avfaudio/avaudiosession/categoryoptions/3727255-overridemutedmicrophoneinterrupt)

  내장 마이크를 음소거할 때 시스템이 오디오 세션을 중단하는지 여부를 나타내는 옵션

---

### 이니셜라이저

- [`init(rawValue: UInt)`](https://developer.apple.com/documentation/avfaudio/avaudiosession/categoryoptions/1624971-init)

  카테고리 옵션 인스턴스를 생성합니다.

## Relationships

---

### Conforms To

- [`OptionSet`](https://developer.apple.com/documentation/swift/optionset)

## See Also

### 오디오 세션 구성하기

- [`var category: AVAudioSession.Category`](https://developer.apple.com/documentation/avfaudio/avaudiosession/1616615-category)

  현재 오디오 세션 카테고리

- [`func setCategory(AVAudioSession.Category)`](https://developer.apple.com/documentation/avfaudio/avaudiosession/1616583-setcategory)

  오디오 세션의 카테고리를 설정합니다.

- [`var availableCategories: [AVAudioSession.Category]`](https://developer.apple.com/documentation/avfaudio/avaudiosession/1616591-availablecategories)

  현재 기기에서 사용할 수 있는 오디오 카테고리 

- [`struct AVAudioSession.Category`](https://developer.apple.com/documentation/avfaudio/avaudiosession/category)

  오디오 세션 카테고리 identifier

- [`var categoryOptions: AVAudioSession.CategoryOptions`](https://developer.apple.com/documentation/avfaudio/avaudiosession/1616503-categoryoptions)

  현재 오디오 세션 카테고리와 관련된 옵션 집합

- [`func setCategory(AVAudioSession.Category, options: AVAudioSession.CategoryOptions)`](https://developer.apple.com/documentation/avfaudio/avaudiosession/1616442-setcategory)

  지정된 옵션으로 오디오 세션의 카테고리를 설정합니다.

- [`var mode: AVAudioSession.Mode`](https://developer.apple.com/documentation/avfaudio/avaudiosession/1616508-mode)

  현재 오디오 세션의 모드

- [`func setMode(AVAudioSession.Mode)`](https://developer.apple.com/documentation/avfaudio/avaudiosession/1616614-setmode)

  오디오 세션의 모드를 설정합니다.

  [`func setCategory(AVAudioSession.Category, mode: AVAudioSession.Mode, options: AVAudioSession.CategoryOptions)`](https://developer.apple.com/documentation/avfaudio/avaudiosession/1771734-setcategory)

  오디오 세션의 카테고리, 모드 및 옵션을 설정합니다.

- [`var availableModes: [AVAudioSession.Mode]`](https://developer.apple.com/documentation/avfaudio/avaudiosession/1616517-availablemodes)

  기기에서 사용할 수 있는 오디오 세션 모드

- [`struct AVAudioSession.Mode`](https://developer.apple.com/documentation/avfaudio/avaudiosession/mode)

  오디오 세션 모드 identifier

- [`var routeSharingPolicy: AVAudioSession.RouteSharingPolicy`](https://developer.apple.com/documentation/avfaudio/avaudiosession/2887118-routesharingpolicy)

  현재 경로(route) 공유 정책

- [`func setCategory(AVAudioSession.Category, mode: AVAudioSession.Mode, policy: AVAudioSession.RouteSharingPolicy, options: AVAudioSession.CategoryOptions)`](https://developer.apple.com/documentation/avfaudio/avaudiosession/2887480-setcategory)

  세션 카테고리, 모드, 경로 공유 정책 및 옵션을 설정합니다.

- [`enum AVAudioSession.RouteSharingPolicy`](https://developer.apple.com/documentation/avfaudio/avaudiosession/routesharingpolicy)

  오디오 세션에서 가능한 경로 공유 정책을 나타내는 케이스