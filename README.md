# ADD-KR
🍎 Apple Developer Document 한국어 번역 프로젝트입니다. [Apple Developer 홈페이지](https://developer.apple.com/documentation/technologies)를 기반으로 번역합니다. [Github](https://github.com/DAEUN28/ADD-KR)에서는 문서 작업만 진행하고 [Gitbook](https://acone1128.gitbook.io/add/)에서 문서를 편리하게 확인할 수 있습니다.

> 질문, 요청사항이 있다면 언제든지 acone1128@gmail.com으로 연락해주세요!
>
> 영어 실력이 부족합니다😂 오역, 오타 지적 언제나 환영합니다 :) 



## 작성방법

> 작성방법, Template을 준수하지 않을 경우, 수정요청되고, 수정사항이 반영되기 전까지 병합될 수 없습니다.
> **문서 단위**: 애플 개발자 문서의 링크와 1:1로 매칭될 수 있습니다. 하나의 문서 == 하나의 파일
>
> 귀찮더라도 꼭 작성방법과 template을 따라주세요❤️

1. 번역을 시작하기 전에 [Issue template](https://github.com/DAEUN28/ADD-KR/blob/main/.github/ISSUE_TEMPLATE/issue-template.md)에 맞춰 **반드시** 이슈를 등록합니다.
2. `Issue Type/생성한 이슈의 번호 - 이슈 제목`으로 브랜치를 생성합니다.
   - 카멜 케이스를 준수해주세요!
3. 생성한 브랜치에서 [Documentation template](https://github.com/DAEUN28/ADD-KR/blob/main/DOCUMENT_TEMPLATE.md)에 맞춰 문서를 작성하고 파일 단위로 커밋합니다.
   - commit message는 `IssueType 파일명 ` 으로 간단명료하게 명시해주세요.
   - commit description에 세부사항을 명시해주세요 :)
4. [PR template](https://github.com/DAEUN28/ADD-KR/blob/main/.github/PULL_REQUEST_TEMPLATE.md)에 맞춰 PR을 생성합니다.
5. 검수 후 문제가 없다면 SUMMARY.md에 문서를 수정하는 작업을 거쳐 main 브랜치로 병합되고, issue 또한 close 됩니다.

> 이슈는 다음 Issue Type 단위에 맞게 생성합니다. 두 개 이상의 Issue Type을 가진 Issue는 생성될 수 없습니다.

### Issue Type

- Create(기존에 없던 문서 생성)
- Refactor(오타 수정, 오역 수정)
- Update(애플 개발자 문서 업데이트에 따른 수정)
- Delete(애플 개발자 문서 업데이트에 따른 삭제)
- Notify(오타 제보, 오역 제보 등 직접 작업하지 않을 예정인 이슈)



## 규칙

1. Swift 문서만 번역합니다.
2. 작성방법, Template을 준수하지 않을 경우, 수정요청되고, 수정사항이 반영되기 전까지 병합될 수 없습니다.
3. 애플 개발자 문서를 기반으로 하되, 애플 개발자 문서에 명시되어 있지 않은 부분(다음 사진의 빨간표시와 같은`분류`)은 Xcode의 Developer Documentation을 기반으로 합니다.

![figure1](https://github.com/DAEUN28/ADD-KR/blob/main/Resource/readme-figure1.png)



## Reference

https://github.com/ESnark/sagwa

https://github.com/tensorflowkorea/tensorflow-kr



## Contributor

프로젝트에 함께 해주세요! :)