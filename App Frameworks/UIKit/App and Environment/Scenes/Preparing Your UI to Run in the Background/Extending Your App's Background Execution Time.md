---
description: 앱이 백그라운드에 진입할 때 중요한 작업이 완료되도록 합니다.
---

# Extending Your App's Background Execution Time

## Info
> **Type**: `Article`
>
> **최근 수정일**: `2021-01-06`
>
> [원문 링크](https://developer.apple.com/documentation/uikit/app_and_environment/scenes/preparing_your_ui_to_run_in_the_background/extending_your_app_s_background_execution_time)

**Framework**

- UIKit

---

## Overview

앱이 백그라운드에서 실행되는 시간을 연장하는 것은 앱이 중요한 작업을 수행하기에 충분한 시간을 보장합니다. 작업이 더 많은 백그라운드 실행 시간을 요구한다면, Background Tasks를 사용하세요.

앱이 백그라운드에 진입할 때, 시스템은 앱델리게이트의 applicationDidEnterBackground(_:)를 호출합니다. 이 메서드는 작업을 수행하고 반환하는데 5초가 소요됩니다. 메서드가 반환되자마자, 시스템은 앱을 suspended 상태로 전환합니다. 대부분의 앱들이 중요한 작업을 수행하기에 5초면 충분하지만, 더 많은 시간이 필요하다면, UIKit에게 앱의 실행 시간 연장을 요청할 수 있습니다.

beginBackgroundTask(withName:expirationHandler:) 메서드를 사용하면 앱의 실행 시간을 연장할 수 있습니다. 이 메서드를 호출하면 중요한 작업을 수행할 수 있는 추가 시간이 제공됩니다.(backgroundTimeRemaining 프로퍼티를 사용하면 백그라운드에서 실행될 수 있는 최대 시간을 확인할 수 있습니다.) 작업이 끝나면 시스템이 작업을 끝났음을 확인할 수 있도록 즉시 endBackgroundTask(_:) 메서드를 호출하세요. 만약 태스크를 적절한 시간에 끝내지 않는다면, 시스템은 앱을 종료시킵니다.

> **Note**
>
> 앱이 백그라운드에 진입해 beginBackgroundTask(withName:expirationHandler:) 메서드를 호출할 때까지 기다리지 마세요. 긴 실행시간이 걸리는 작업이 실행되기 전에 메서드를 호출하세요.

Listing 1은 서버에 데이터를 저장하는데 5초 이상 소요될 수 있는 백그라운드 작업을 설정하는 예제입니다. beginBackgroundTask(withName:expirationHandler:) 메서드는 Identifier를 반환합니다. 반환된 Identifier는 endBackgroundTask(_:) 메서드에 전달하기 위해 반드시 저장해야 합니다.

**Listing 1** Extending the app's background execution time

```swift
func sendDataToServer( data : NSData ) {
   // Perform the task on a background queue.
   DispatchQueue.global().async {
      // Request the task assertion and save the ID.
      self.backgroundTaskID = UIApplication.shared.
                 beginBackgroundTask (withName: "Finish Network Tasks") {
         // End the task if time expires.
         UIApplication.shared.endBackgroundTask(self.backgroundTaskID!)
         self.backgroundTaskID = UIBackgroundTaskInvalid
      }
            
      // Send the data synchronously.
      self.sendAppDataToServer( data: data)
            
      // End the task assertion.
      UIApplication.shared.endBackgroundTask(self.backgroundTaskID!)
      self.backgroundTaskID = UIBackgroundTaskInvalid
   }
}
```

> **Note**
>
> 앱 익스텐션에서는 beginBackgroundTask(withName:expirationHandler:) 메서드를 호출할 수 없습니다. 대신 앱 익스텐션에서 추가 실행 시간을 요청하기 위해, ProcessInfo의 performExpiringActivity(withReason:using:) 메서드를 호출하세요.

## See Also

### 백그라운드 실행

---

- **Updating Your App with Background App Refresh**

  백그라운드에서 기회에 따라 컨텐츠를 가져오고 앱의 인터페이스를 업데이트합니다.

- **About the Background Execution Sequence**

  앱이 백그라운드에 진입할 때 사용자의 코드가 실행되는 순서를 알아봅니다.