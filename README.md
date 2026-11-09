# Car Challenge Starter

현대자동차그룹 차량용 앱 개발 공모전을 위한 최소 Android Automotive 프로젝트입니다. 앱 아이디어, 차량 데이터 접근, 계정 정보는 아직 정하지 않았습니다.

## 현재 구성

- Kotlin 단일 `Activity`와 실행 확인 화면
- `minSdk` 28, `targetSdk` 34, `compileSdk` 37
- Android Gradle Plugin 9.5.1, Gradle 9.6.0
- 차량용 기기 선언과 앱 실행 진입점
- 차량 권한, Pleos SDK, 네트워크 권한은 기능이 정해지면 추가

## Android Studio에서 열기

1. Android Studio에서 이 폴더를 프로젝트로 엽니다.
2. SDK Manager에서 Android API 37 SDK Platform이 설치되어 있는지 확인합니다. Android Studio의 Gradle JDK는 17 이상으로 설정합니다.
3. Gradle Sync를 실행합니다. 최초 실행에는 Android Gradle Plugin과 Gradle 다운로드가 필요합니다. 명령줄에서는 `gradlew.bat assembleDebug`로 빌드할 수 있습니다.
4. Pleos Connect 전용 AVD를 설치해 실행한 다음 `app`을 빌드하고 실행합니다.

Pleos 공식 문서는 `minSdk` 28 이상과 전용 AVD를 요구합니다. 차량 기능 검증에는 일반 휴대전화 에뮬레이터 대신 Pleos Connect 전용 AVD를 사용합니다. 로컬 SDK에 API 34 Pleos Connect v2.1.0 이미지가 설치되어 있으며, `Pleos Connect v2.1.0` AVD가 생성되었습니다.

## 아이디어가 정해진 뒤

1. 앱 이름과 `applicationId`를 확정합니다.
2. 사용자 흐름에 맞춰 화면과 상태를 추가합니다.
3. 실제로 쓸 Pleos SDK 버전과 Maven 저장소를 확인해 의존성을 추가합니다.
4. 사용하는 차량 API의 권한만 Manifest에 선언합니다.
5. 전용 AVD에서 API 지원 범위, 값 조회, 오류와 구독 해제를 확인합니다.

Vehicle SDK Sample App 가이드의 기준은 SDK 2.3.2, Service 2.3.22, Pleos Connect v2.1 AVD입니다. 이 샘플의 `minSdk` 23과 제품 앱의 최소 API 28 요구사항은 서로 다릅니다. 샘플 버전과 제품 앱에 적용할 SDK 버전은 연동 시점에 공식 문서와 실제 AVD 상태로 다시 확인합니다.

## 참고 문서

- [Pleos Connect 개발 시작](https://document.pleos.ai/docs/pleos-only/getting-started)
- [Pleos Connect 에뮬레이터 설치](https://document.pleos.ai/docs/connect/guide/getting-started/application-development/setup-connect-sdk-emulator)
- [공모전 참가 규정](https://appdevchallenge.auto-hmg.io/guide/rules)
