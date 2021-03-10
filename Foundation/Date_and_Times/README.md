---
description: 날짜와 시간을 비교하고, 달력 및 시간대 계산을 수행합니다.
---

# Date and Times

## Info
> **Type**: `Collection`
>
> **최근 수정일**: `2021-03-06`
>
> [원문 링크](https://developer.apple.com/documentation/foundation/dates_and_times)

**Framework**

- Foundation

## Topics

---

### 날짜 표현

- [`struct Date`](Date.md)

  달력 또는 표준 시간대와 관계없는 특정 시점

- [`struct DateInterval`](https://developer.apple.com/documentation/foundation/dateinterval)

  특정 시작 날짜와 종료 날짜 사이의 시간 범위

- [`typealias TimeInterval`](https://developer.apple.com/documentation/foundation/timeinterval)

  초 단위 숫자

---

### 달력에 관한 계산

- [`struct DateComponents`](https://developer.apple.com/documentation/foundation/datecomponents)

  달력 시스템 및 표준 시간대에서 평가할 단위(예: 년, 월, 일, 시간 및 분)로 지정된 날짜 또는 시간

- [`struct Calendar`](https://developer.apple.com/documentation/foundation/calendar)

  달력 단위(예: 시대, 연도 및 주중)와 절대 시점 간의 관계를 정의하여, 날짜 계산 및 비교 기능을 제공합니다.

- [`struct TimeZone`](https://developer.apple.com/documentation/foundation/timezone)

  특정 지정학적 지역과 관련된 표준 시간 규약에 대한 정보

---

### 날짜 형식

- [`class DateFormatter`](https://developer.apple.com/documentation/foundation/dateformatter)

  날짜와 텍스트 표현을 변환하는 formatter

- [`class DateComponentsFormatter`](https://developer.apple.com/documentation/foundation/datecomponentsformatter)

  시간 양의 문자열 표현을 생성하는 formatter

- [`class DateIntervalFormatter`](https://developer.apple.com/documentation/foundation/dateintervalformatter)

  시간 간격의 문자열 표현을 생성하는 formatter

- [`class ISO8601DateFormatter`](https://developer.apple.com/documentation/foundation/iso8601dateformatter)

  날짜와 해당 ISO 8601 문자열 표현을 변환하는 formatter

---

### 국제화

- [`struct Locale`](https://developer.apple.com/documentation/foundation/locale)

  표시를 위한 데이터 형식화에 사용되는 언어, 문화 및 기술 규약에 대한 정보

---

## See Also

---

- [Numbers, Data, and Basic Values](https://developer.apple.com/documentation/foundation/numbers_data_and_basic_values)

  코코아 전체에서 사용되는 기본 값 및 기타 기본 유형으로 작업하세요.

- [Strings and Text](https://developer.apple.com/documentation/foundation/strings_and_text)

  유니코드 문자의 문자열을 생성 및 처리하고, 정규식을 사용해 패턴을 찾고, 텍스트의 자연어 분석을 수행합니다.

- [Collections](https://developer.apple.com/documentation/foundation/collections)

  배열, 딕셔너리, set 및 특수 컬렉션을 사용해 객체 또는 값 그룹을 저장하고, 반복합니다.

- [Units and Measurement](https://developer.apple.com/documentation/foundation/units_and_measurement)

  locale-aware 형식화 및 관련 단위 간의 변환을 허용하기 위해 숫자 양에 물리적인 치수를 라벨로 표시합니다.

- [Data Formatting](https://developer.apple.com/documentation/foundation/data_formatting)

  locale-aware 문자열 표현으로부터 숫자, 날짜, 측정 값 및 기타 값을 변환합니다.

- [Filters and Sorting](https://developer.apple.com/documentation/foundation/filters_and_sorting)

  속성(predicates), 표현식 및 sort descriptors를 사용해 컬렉션 및 기사 서비스의 요소를 검사하세요.

