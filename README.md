# WORK SAFE NOTE2 — APK 배포 전용

WORK SAFE NOTE2를 **APK 파일만으로 배포**하기 위한 GitHub 저장소야. 기존 `test`와 `jun2026` 저장소는 변경하지 않아.

## APK 올리는 방법

1. [incoming 폴더](https://github.com/lovebank198307291-hue/work-safe-note2/tree/main/incoming)에서 **Add file → Upload files**를 눌러.
2. 새 APK 파일 한 개를 업로드하고 **Commit changes**를 눌러.
3. [Actions](https://github.com/lovebank198307291-hue/work-safe-note2/actions)의 `Publish APK Release`가 성공했는지 확인해.
4. 성공하면 [Releases](https://github.com/lovebank198307291-hue/work-safe-note2/releases)에서 버전별 `WORK_SAFE_NOTE.apk`를 다운로드할 수 있어.

- 업로드 파일명은 자유롭게 써도 돼. 예: `app-debug(6).apk`, `WSN_v1.0.8.apk`.
- 최초 업로드 예정: `v1.0.7` / `versionCode 8`.
- 이후 업데이트에서는 `versionName`과 `versionCode`를 모두 높여야 해.
- **패키지명 `com.safetyladder.app`과 APK 서명 인증서를 반드시 유지해야 해.** 자동 빌드가 아니라 *기존 APK 서명을 검증하고 Release에 첨부*하는 기능이야.
- 본 저장소는 공개 저장소야. APK에는 내부 코드·인증값이 포함될 수 있으니 공개 배포 전에 확인해.

## 최신 APK 다운로드

Release가 하나라도 게시된 뒤에 아래 링크가 작동해:

https://github.com/lovebank198307291-hue/work-safe-note2/releases/latest/download/WORK_SAFE_NOTE.apk

## 앱 내 업데이트 관련 주의

**현재 v1.0.7 APK는 `jun2026` 저장소를 조회해.** 그러므로 이 저장소에서 Release를 만들어도 *이미 설치한 v1.0.7 앱은 새 저장소의 Release를 자동으로 감지하지 못해*. 이후 앱의 업데이트 주소를 `work-safe-note2`로 변경하여 **같은 서명키로** 새 APK를 빌드해야 해.

Android는 APK 설치 시 사용자의 승인이 필요해. GitHub Release만으로 기존 APK에 자동 설치 기능이 생기지 않아.

## 보안 및 실패 조건

자동 게시 과정에서 `apksigner`로 서명 블록을 확인하고 최초 APK와 동일한 인증서 지문인지 검사해. `versionCode` 역행·중복 버전은 게시하지 않아. 파일이나 서명이 잘못된 경우 Actions 로그에 원인이 표시돼.

기준 인증서 SHA-256:
`9db354ed6b724bb259727b761a33f41f914332adac131d246761b2401e77e7b2`
