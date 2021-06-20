# ADD-KR

🍎 Apple Developer Document 한국어 번역 프로젝트입니다. [Apple Developer 홈페이지](https://developer.apple.com)를 기반으로 번역합니다. [Github](https://github.com/DAEUN28/ADD-KR)에서는 문서 작업만 진행하고 [Gitbook](https://acone1128.gitbook.io/add/)에서 문서를 편리하게 확인할 수 있습니다. 

> 질문, 요청사항이 있다면 언제든지 acone1128@gmail.com으로 연락해주세요!
>
> 영어 실력이 부족합니다😂 오역, 오타 지적 언제나 환영합니다 :)

**DocC의 등장으로 DocC 기반으로 마이그레이션을 위 해당 프로젝트는 아카이브될 예정입니다. 새로운 [레포지토리](https://github.com/ADD-KR/ADD-KR)로 마이그레이션 중입니다...**

# 규칙

- Swift 문서만 번역합니다.
- 리소스 등의 모든 경로는 상대 경로이며, 모든 파일명과 폴더명의 띄어쓰기는 언더바(_)로 대체합니다.
- 규칙을 준수하지 않을 경우, 수정요청되고, 수정사항이 반영되기 전까지 병합될 수 없습니다.
- 문서 단위는 애플의 링크와 1:1로 매칭될 수 있는 하나의 문서입니다.
  - 하나의 문서 == 하나의 파일 == 애플 링크 

## 작업방법

1. 번역을 시작하기 전에 [Issue template](.github/ISSUE_TEMPLATE/issue-template.md)에 맞춰 **반드시** 이슈를 등록합니다.
2. `Issue type/이슈 번호 - 문서명`으로 브랜치를 생성합니다.
   * 케밥케이스를 준수해주세요.
   * 예시: create/#1-appleSlicon
3. 생성한 브랜치에서 [문서 템플릿](/DOCUMENT_TEMPLATE)에 맞춰 문서를 작성하고 파일 단위로 커밋합니다.
   * commit message는 Create AppleSilicon과 같이 간단명료하게 명시해주세요.
   * commit description에 세부사항을 명시해주세요 :)
4. [PR template](.github/PULL_REQUEST_TEMPLATE.md)에 맞춰 PR을 생성합니다.
5. 검수 후 문제가 없다면 각 분류 브랜치의 SUMMARY.md에 문서를 수정하는 작업을 거쳐 해당 분류의 브랜치로 병합되고, issue 또한 close 됩니다.
   * SUMMARY.md를 수정하는 작업을 하면서 gitbook이 파싱할 수 없을만큼 길이가 긴 url은 임의로 변경될 수 있습니다.

## Reference

[https://github.com/ESnark/sagwa](https://github.com/ESnark/sagwa)

[https://github.com/tensorflowkorea/tensorflow-kr](https://github.com/tensorflowkorea/tensorflow-kr)

## Contributor

프로젝트에 함께 해주세요! :\)

