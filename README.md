# 반급식 알림 APK 프로젝트

Android Studio에서 열어서 APK로 빌드하는 프로젝트입니다.

## 기능

- 1, 2, 3학년 각각 반 수 설정
- 기준 시작일 설정
- 매주 한 반씩 밀리는 급식 순서 자동 계산
- 3반씩 묶어서 표시
- 알림 요일/시간 설정
- 매주 알림 예약
- 테스트 알림 발송
- 휴대폰 재부팅 후 알림 재예약

## 순서 계산 예시

9반 기준:

- 1주차: `1,2,3 / 4,5,6 / 7,8,9`
- 2주차: `2,3,4 / 5,6,7 / 8,9,1`
- 3주차: `3,4,5 / 6,7,8 / 9,1,2`

10반처럼 3으로 나누어떨어지지 않으면 마지막 묶음은 중복 없이 표시합니다.

- 1주차: `1,2,3 / 4,5,6 / 7,8,9 / 10`
- 2주차: `2,3,4 / 5,6,7 / 8,9,10 / 1`

## Android Studio에서 APK 만들기

1. Android Studio 실행
2. `File > Open`에서 이 폴더 선택
3. Gradle Sync 실행
4. `Build > Build Bundle(s) / APK(s) > Build APK(s)` 클릭
5. 빌드 완료 후 `app/build/outputs/apk/debug/app-debug.apk` 확인

## 설치 시 주의

- Android 13 이상에서는 앱 첫 실행 후 알림 권한을 허용해야 알림이 뜹니다.
- 기기 절전 상태나 제조사 배터리 최적화 때문에 알림이 몇 분 늦을 수 있습니다.
- 이 앱은 서버를 사용하지 않고, 모든 설정은 기기 내부에만 저장됩니다.

## 태블릿만으로 APK 만들기: GitHub Actions

1. GitHub에서 새 repository를 만듭니다.
2. 이 프로젝트 폴더의 모든 파일을 repository에 업로드합니다.
3. repository의 `Actions` 탭으로 이동합니다.
4. `Build APK` 워크플로를 선택합니다.
5. `Run workflow`를 누릅니다.
6. 완료 후 아래 `Artifacts`에서 `MealClassAlarm-debug-apk`를 다운로드합니다.
7. ZIP을 풀면 `app-debug.apk`가 나옵니다.
