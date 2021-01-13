---
description: 데이터 모델의 변경 사항이 경량 마이그레이션의 역량을 초과하는 드문 경우에 중량(수동) 마이그레이션을 사용합니다.
---

# Heavyweight Migration

## Info

> **Type**: `Collection`
>
> **최근 수정일**: `2021-01-13`
>
> [원문 링크](https://developer.apple.com/documentation/coredata/heavyweight_migration)

**Framework**

* Core Data

## Topics

### 엔티티 매핑

* class NSMigrationManager

  지정된 매핑 모델을 사용해 한 영구 저장소에서 다른 저장소로 데이터를 마이그레이션하는 마이그레이션 매니저 인스턴스

* class NSMappingModel

  엔티티를 원본에서 대상 관리\(managed\) 객체 모델으로 어떻게 매핑할지 명시하는 모델 인스턴스

* class NSEntityMapping

  엔티티를 원본에서 대상 관리\(managed\) 객체 모델으로 어떻게 매핑할지 명시하는 매핑 인스턴스

* class NSEntityMigrationPolicy

  엔티티 매핑에 대한 마이그레이션 프로세스를 커스텀하는 정책\(policy\) 인스턴스

* enum NSEntityMappingType

  원본 모델과 대상 모델 사이 엔티티를 매핑하기위한 타입

* class NSPropertyMapping

  원본 엔티티의 프로퍼티를 대상 엔티티의 프로퍼티로 매핑하는 방법을 모델에서 명시하는 매핑 인스턴스

## See Also

### 데이터 마이그레이션

* [Using Lightweight Migration](using-lightweight-migration.md)

  경량\(자동\) 마이그레이션을 요청하여 앱의 변경사항에 맞게 데이터 모델을 업데이트합니다.

