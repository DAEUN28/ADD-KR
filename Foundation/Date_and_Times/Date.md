---
description: 달력 또는 표준 시간대와 관계없는 특정 시점
---

# Date

## Info

> **Type**: `Structure`
>
> **최근 수정일**: `2021-03-06`
>
> [원문 링크](https://developer.apple.com/documentation/foundation/date)

**Availability**

- iOS 7.0+
- macOS 10.9+
- Mac Catalyst 13.0+
- tvOS 9.0+
- watchOS 2.0+
- Xcode 8.0+

**Framework**

- Foundation

## Declaration

```swift
struct Date
```

## Overview

Date 값은 특정 캘린더 시스템 또는 표준 시간대와 관계없이 한 시점을 캡슐화합니다. Date 값은 절대 참조 날짜에 상대적인 시간 간격을 나타냅니다.

Date 구조체는 날짜를 비교하고, 두 날짜 간의 시간 간격을 계산하며, 다른 날짜에 상대적인 시간 간격에서 새로운 날짜를 생성하는 메서드를 제공합니다. [DateFormatter](https://developer.apple.com/documentation/foundation/dateformatter) 인스턴스와 함께 날짜 값을 사용해 날짜 및 시간의 지역화된 표현을 만들고 [Calendar](https://developer.apple.com/documentation/foundation/calendar) 인스턴스와 함께 달력 산수를 수행합니다.

Date는 [NSDate](https://developer.apple.com/documentation/foundation/nsdate) 클래스와 연결됩니다. Objective-C API와 상호작용하는 코드에서 상호 교환하여 사용할 수 있습니다.

## Topics

### 날짜 생성

---

- [`init()`](https://developer.apple.com/documentation/foundation/date/1780470-init)

  현재 날짜 및 시간으로 초기화된 날짜 값을 생성합니다.

- [`init(timeIntervalSinceNow: TimeInterval)`](https://developer.apple.com/documentation/foundation/date/1780053-init)

  현재 날짜 및 시간을 기준으로 주어진 초 단위 숫자만큼 초기화된 날짜 값을 생성합니다.

- [`init(timeInterval: TimeInterval, since: Date)`](https://developer.apple.com/documentation/foundation/date/1779905-init)

  주어진 날짜를 기준으로 주어진 초 단위 숫자만큼 초기화된 날짜 값을 생성합니다.

- [`init(timeIntervalSinceReferenceDate: TimeInterval)`](https://developer.apple.com/documentation/foundation/date/1779647-init)

  2001년 1월 1일 00:00:00 UTC를 기준으로 주어진 초단위 시간만큼 초기화된 날짜 값을 생성합니다.

- [`init(timeIntervalSince1970: TimeInterval)`](https://developer.apple.com/documentation/foundation/date/1780353-init)

  1970년 1월 1일 00:00:00 UTC를 기준으로 주어진 초단위 시간만큼 초기화된 날짜 값을 생성합니다.

### 시간 경계 얻기

- [`static let distantFuture: Date`](https://developer.apple.com/documentation/foundation/date/1779684-distantfuture)

  먼 미래의 날짜를 나타내는 날짜 값

- [`static let distantPast: Date`](https://developer.apple.com/documentation/foundation/date/1779829-distantpast)

  먼 과거의 날짜를 나타내는 날짜 값

### 날짜 비교

---

- [`static func < (Date, Date) -> Bool`](https://developer.apple.com/documentation/foundation/date/2293238)

  왼쪽 날짜가 오른쪽 날짜보다 빠른 경우 true인 Boolean 값을 반환합니다.

- [`static func == (Date, Date) -> Bool`](https://developer.apple.com/documentation/foundation/date/2293580)

  두 날짜 값이 동일한 시점을 나타내는 경우 true인 Boolean 값을 반환합니다.

- [`func compare(Date) -> ComparisonResult`](https://developer.apple.com/documentation/foundation/date/1780430-compare)

  두 날짜 값을 비교합니다.

### 시간 간격 얻기

---

- [`func timeIntervalSince(Date) -> TimeInterval`](https://developer.apple.com/documentation/foundation/date/1779636-timeintervalsince)

  리시버와 다른 주어진 날짜 사이의 간격을 반환합니다.

- [`var timeIntervalSinceNow: TimeInterval`](https://developer.apple.com/documentation/foundation/date/1780473-timeintervalsincenow)

  현재 날짜 및 시간과 date 값 사이의 시간 간격

- [`var timeIntervalSinceReferenceDate: TimeInterval`](https://developer.apple.com/documentation/foundation/date/1780268-timeintervalsincereferencedate)

  2001년 1월 1일 00:00:00 UTC와 date 값 사이의 간격

- [`var timeIntervalSince1970: TimeInterval`](https://developer.apple.com/documentation/foundation/date/1779963-timeintervalsince1970)

  1970년 1월 1일 00:00:00 UTC와 date 값 사이의 간격

- [`static var timeIntervalSinceReferenceDate: TimeInterval`](https://developer.apple.com/documentation/foundation/date/1780165-timeintervalsincereferencedate)

  2001년 1월 1일 00:00:00 UTC와 현재 날짜 및 시간 사이의 간격

- [`static let timeIntervalBetween1970AndReferenceDate: Double`](https://developer.apple.com/documentation/foundation/date/1779987-timeintervalbetween1970andrefere)

  1970년 1월 1일부터 참조날짜인 2001년 1월 1일까지의 초단위 숫자

### 시간 간격 더하기 또는 빼기

---

- [`static func != (Date, Date) -> Bool`](https://developer.apple.com/documentation/foundation/date/2883071)

  두 값이 같지 않은지 여부를 나타내는 Boolean 값을 반환합니다.

- [`static func + (Date, TimeInterval) -> Date`](https://developer.apple.com/documentation/foundation/date/2293740)

  지정된 시간을 더한 날짜를 반환합니다.

- [`static func += (inout Date, TimeInterval)`](https://developer.apple.com/documentation/foundation/date/2293123)

  날짜에 시간간격을 더합니다.

- [`static func - (Date, TimeInterval) -> Date`](https://developer.apple.com/documentation/foundation/date/2293436)

  지정된 시간에서 뺀 날짜를 반환합니다.

- [`static func -= (inout Date, TimeInterval)`](https://developer.apple.com/documentation/foundation/date/2293513)

  날짜에서 시간간격을 뺍니다.

- [`static func < (Date, Date) -> Bool`](https://developer.apple.com/documentation/foundation/date/2293238)

  왼쪽 날짜가 오른쪽 날짜보다 빠른 경우 true인 Boolean 값을 반환합니다.

- [`static func <= (Date, Date) -> Bool`](https://developer.apple.com/documentation/foundation/date/2883236)

  첫 번째 인수의 값이 두 번째 인수의 값보다 작거나 같은지 여부를 나타내는 Boolean 값을 반환합니다.

- [`static func == (Date, Date) -> Bool`](https://developer.apple.com/documentation/foundation/date/2293580)

  두 날짜 값이 동일한 시점을 나타내는 경우 true인 Boolean 값을 반환합니다.

- [`static func >= (Date, Date) -> Bool`](https://developer.apple.com/documentation/foundation/date/2882995)

  첫 번째 인수의 값이 두 번째 인수의 값보다 크거나 같은지 여부를 나타내는 Boolean 값을 반환합니다.

### 날짜 설명

---

- [`var description: String`](https://developer.apple.com/documentation/foundation/date/1779759-description)

  날짜 값에 대한 텍스트 설명

- [`func description(with: Locale?) -> String`](https://developer.apple.com/documentation/foundation/date/1780034-description)

  주어진 locale을 사용해 날짜의 문자열 표현을 반환합니다.

- [`var debugDescription: String`](https://developer.apple.com/documentation/foundation/date/1779828-debugdescription)

  디버깅에 적합한 날짜에 대한 텍스트 설명

- [`var customMirror: Mirror`](https://developer.apple.com/documentation/foundation/date/2427168-custommirror)

  날짜를 반영하는 Mirror

- [`var hashValue: Int`](https://developer.apple.com/documentation/foundation/date/1779628-hashvalue)

  날짜의 계산된 hash 값

### 참조 유형 사용

---

- [`class NSDate`](https://developer.apple.com/documentation/foundation/nsdate)

  Date와 연결되는 특정 시점의 표현입니다. 참조 의미론(refrence semantics) 또는 기타 Foundation 특정 동작이 필요할 떄, NSDate를 사용하세요. 

- [`typealias Date.ReferenceType`](https://developer.apple.com/documentation/foundation/date/referencetype)

  이 값 타입의 해당 참조 참조타입에 대한 별칭

### Type Aliases

---

- [`typealias Date.Stride`](https://developer.apple.com/documentation/foundation/date/stride)

### Initializers

---

- [`init(from: Decoder)`](https://developer.apple.com/documentation/foundation/date/2895247-init)

### Instance Methods

---

- [`func addTimeInterval(TimeInterval)`](https://developer.apple.com/documentation/foundation/date/1948949-addtimeinterval)

  이 날짜에 시간 간격을 더합니다.

- [`func addingTimeInterval(TimeInterval) -> Date`](https://developer.apple.com/documentation/foundation/date/1948745-addingtimeinterval)

  이 날짜에 시간 간격을 더해 새로운 날짜 값을 생성합니다.

- [`func advanced(by: TimeInterval) -> Date`](https://developer.apple.com/documentation/foundation/date/3329237-advanced)

- [`func distance(to: Date) -> TimeInterval`](https://developer.apple.com/documentation/foundation/date/3329238-distance)

- [`func encode(to: Encoder)`](https://developer.apple.com/documentation/foundation/date/2895072-encode)

- [`func hash(into: inout Hasher)`](https://developer.apple.com/documentation/foundation/date/3236722-hash)

### Operator Functions

---

- [`static func ... (Date) -> PartialRangeFrom`](https://developer.apple.com/documentation/foundation/date/2963300)

  하한에서 위쪽으로 확장된 부분 범위를 반환합니다.

- [`static func ... (Date) -> PartialRangeThrough`](https://developer.apple.com/documentation/foundation/date/2963303)

  상한을 포함하여 부분 범위를 반환합니다.

- [`static func ... (Date, Date) -> ClosedRange`](https://developer.apple.com/documentation/foundation/date/2949100)

  두 경계를 모두 포함하는 닫힌 범위를 반환합니다.

- [`static func ..< (Date) -> PartialRangeUpTo`](https://developer.apple.com/documentation/foundation/date/2895066)

  상한을 포함하지 않는 부분 범위를 반환합니다.

- [`static func ..< (Date, Date) -> Range`](https://developer.apple.com/documentation/foundation/date/2949112)

  하한은 포함하지만 상한은 포함하지 않는 반 개방 범위를 반환합니다.

- [`static func > (Date, Date) -> Bool`](https://developer.apple.com/documentation/foundation/date/2963306)

  첫 번째 인수의 값이 두 번째 인수의 값보다 큰지 여부를 나타내는 Boolean 값을 반환합니다.

## Relationships

### Conforms To

---

- [`CKRecordValueProtocol`](https://developer.apple.com/documentation/cloudkit/ckrecordvalueprotocol)
- [`Comparable`](https://developer.apple.com/documentation/swift/comparable)
- [`CustomDebugStringConvertible`](https://developer.apple.com/documentation/swift/customdebugstringconvertible)
- [`CustomReflectable`](https://developer.apple.com/documentation/swift/customreflectable)
- [`CustomStringConvertible`](https://developer.apple.com/documentation/swift/customstringconvertible)
- [`Decodable`](https://developer.apple.com/documentation/swift/decodable)
- [`Encodable`](https://developer.apple.com/documentation/swift/encodable)
- [`Equatable`](https://developer.apple.com/documentation/swift/equatable)
- [`ReferenceConvertible`](https://developer.apple.com/documentation/foundation/referenceconvertible)

## See Also

### 날짜 표현

- [`struct DateInterval`](https://developer.apple.com/documentation/foundation/dateinterval)

  특정 시작 날짜와 종료 날짜 사이의 시간 범위

- [`typealias TimeInterval`](https://developer.apple.com/documentation/foundation/timeinterval)

  초 단위 숫자