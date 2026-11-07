# WORK SAFE NOTE2 · APK 업데이트 저장소

이 저장소는 `WORK SAFE NOTE2` APK의 다운로드와 업데이트 배포용이야. 다른 저장소 `test`, `jun2026`은 변경하지 않아.

## 최신 기준 APK
- 버전: **v1.0.8** (`versionCode 9`)
- 패키지: `com.safetyladder.app`
- 기존 v1.0.7과 **동일한 서명 인증서**
- 앱 업데이트 조회: `work-safe-note2` GitHub Releases
- 인증서 SHA-256: `9db354ed6b724bb259727b761a33f41f914332adac131d246761b2401e77e7b2`
- 업로드 예정 APK SHA-256: `459b63618e0659555b86dedc462d54c9c9100b8f202dde8c6d68573edfacc340`

## 현재 배포 상태

- **v1.0.8 Release 게시 완료.** APK 이름, 크기, SHA-256이 사용자가 제공한 파일과 동일함.
- **v1.0.8은 다시 업로드하지 마.** GitHub Actions는 이미 존재하는 같은 버전의 Release를 중복 생성하지 않음.
- **다음 v1.0.9부터** 아래 APK 업로드 절차를 사용하면 돼. 자동 게시 workflow는 아직 새 버전의 실제 성공 사례가 없어 후속 검증이 필요함.

## APK만 업로드하기
1. [incoming 폴더](https://github.com/lovebank198307291-hue/work-safe-note2/tree/main/incoming)로 이동
2. **Add file → Upload files**로 `WORK_SAFE_NOTE.apk` 업로드
3. **Commit changes** 누르기
4. [Actions](https://github.com/lovebank198307291-hue/work-safe-note2/actions)에서 **Publish APK Release** 성공 확인
5. 성공하면 Release 태그 `v1.0.8`과 `WORK_SAFE_NOTE.apk`가 자동 게시됨

### 최신 APK 다운로드
https://github.com/lovebank198307291-hue/work-safe-note2/releases/latest/download/WORK_SAFE_NOTE.apk

**첫 Release가 성공한 뒤부터** 위 링크가 작동해.

## 다음 버전 업데이트
- `versionName`을 `1.0.9` 이상으로 올리기
- `versionCode`를 `10` 이상으로 올리기
- **같은 패키지명과 서명키**를 사용해 빌드하기
- 새 APK를 다시 `incoming`에 업로드하면 서명과 버전 검증 후 새 Release를 게시함
- 앱은 신규 Release를 확인하고 다운로드를 안내함. 설치는 Android에서 사용자가 직접 승인해야 함

## 보안
저장소가 **공개(Public)** 상태이므로 업로드한 APK는 누구나 내려받을 수 있어. 앱에 포함된 내부 인증정보·API 키가 없는지 배포 전에 확인해. **`debug.keystore` 등의 개인 서명키는 GitHub에 업로드하지 말 것.**

## 검증 범위
APK 압축 무결성, 내장 버전명/코드, 패키지명, APK v2 서명 인증서, 업데이트 저장소 문자열을 확인했어. 실제 Android 기기 설치 및 GitHub Actions 성공은 APK를 게시한 뒤 별도 확인이 필요해.
