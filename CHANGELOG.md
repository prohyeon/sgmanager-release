# Changelog

## v0.2.1

- STOVE 정상 종료 중 `메인 윈도우를 찾을 수 없습니다` 오류가 발생할 때 원인 추적용 진단 로그를 남기도록 개선했습니다.
- 진단 로그에는 STOVE 프로세스 상태, top-level 윈도우의 `hwnd`, `pid`, 클래스명, 제목, 실행 파일 경로, 후보 탈락 사유가 포함됩니다.
- 메인 화면의 `API 테스트` 버튼 옆에 `로그` 버튼을 추가해 진단 로그를 서브창에서 확인할 수 있도록 했습니다.
- 로그 서브창에 새로고침과 바탕화면 export 기능을 추가했습니다.
- SGManager 내부 버전과 Windows 실행 파일 버전을 0.2.1로 업데이트했습니다.

## v0.2.0

- 리워드샵의 `이번 달 획득` 조회를 최신 공식 API 계약에 맞춰 수정했습니다.
- 월간 획득 플레이크 조회 시 `yyyyMM`과 `tz_offset`을 사용하도록 변경해 표시 실패 가능성을 줄였습니다.
- SGManager 내부 버전과 Windows 실행 파일 버전을 0.2.0으로 업데이트했습니다.

## v0.1.10

- 딸깍 ALL에서 각 계정의 자동화 작업이 끝난 뒤 플레이크 잔액을 다시 조회하도록 변경했습니다.
- 여러 계정을 순차 처리할 때 계정별 로그인 세션 토큰으로 잔액을 조회하고, 다음 계정 로그인 전에 해당 계정 목록 행을 갱신하도록 검증했습니다.
- SGManager 앱 버전과 Windows 실행 파일 버전을 0.1.10으로 업데이트했습니다.

## v0.1.9

- 딸깍 ALL 실행 중에도 각 계정의 세션 토큰이 준비되면 플레이크 잔액을 조회해 계정 목록 오른쪽에 표시하도록 개선했습니다.
- 선택한 계정부터 딸깍 ALL을 시작해도 플레이크 잔액이 원래 계정 행에 맞게 갱신되도록 수정했습니다.
- SGManager 앱 버전과 Windows 실행 파일 버전을 0.1.9로 업데이트했습니다.

## v0.1.8

- ACCOUNTS 목록에 로그인 성공 후 플레이크 잔액이 함께 표시되도록 개선했습니다.
- STOVE 종료 버튼과 로그인 전 기존 STOVE 정리에 정상 종료 요청 후 실제 프로세스 종료 대기 방식을 적용했습니다.
- 출석 게임 종료도 기본적으로 정상 종료 요청을 사용하도록 변경했습니다.
- 게임 설정에 `STOVE/게임 강제 종료 사용` 체크박스를 추가해 필요한 경우 기존 강제 종료 방식을 선택할 수 있게 했습니다.
- SGManager 앱 버전과 Windows 실행 파일 버전을 0.1.8로 업데이트했습니다.

## v0.1.7

- SSO state POST 요청 후 profile Chrome을 열기 전에 기존 Chrome 창 존재 여부를 확인하도록 개선했습니다.
- 기존 Chrome 창이 열려 있으면 안전하게 종료한 뒤 새 profile Chrome을 열어 Google 로그인 이후 뒤쪽 Chrome 창을 잘못 인식하는 문제를 줄였습니다.
- 직접 프로필 열기, 딸깍 전체 자동화, SSO 진단의 브라우저 열기 경로에 동일한 사전 종료 처리를 적용했습니다.
- SGManager 앱 버전과 Windows 실행 파일 버전을 0.1.7로 업데이트했습니다.

## v0.1.6

- 기존 Chrome 창이 열려 있어도 새로 열린 STOVE 프로필 Chrome 창을 우선 인식하도록 개선했습니다.
- 전체 자동화 버튼 탐색과 좌표 fallback이 방금 연 Chrome 창을 먼저 사용하도록 수정했습니다.
- Google 로그인 후 Chrome 창이 여러 개 있을 때 뒤쪽 창을 잘못 대상으로 잡는 문제를 완화했습니다.
- SGManager 앱 버전과 Windows 실행 파일 버전을 0.1.6으로 업데이트했습니다.

## v0.1.5

- Places SGManager at the upper-left work area on startup to reduce Chrome overlap.
- Minimizes SGManager during click-all runs and restores it before showing completion or error results.
- Opens Chrome in the right half of the work area and corrects the window bounds after launch.
- Updates SGManager app and Windows executable versions to 0.1.5.

## v0.1.4

- Shows `[SG] ING (작업중)` in the Chrome title while full automation is running.
- Retries the full automation button click once after 5 seconds when Chrome remains open and idle.
- Updates SGManager app and Windows executable versions to 0.1.4.

## v0.1.3

- Closes Chrome through WM_CLOSE during token capture instead of force-killing it.
- Keeps STOVE launcher fallback and attendance-game process cleanup on `taskkill /F`.
- Updates SGManager app and Windows executable versions to 0.1.3.

## v0.1.2

- Adds public release channel configuration for in-app update checks.
- Adds click-all controls for selecting the starting account and stopping runs.
- Keeps local capture artifacts out of source history.

## v0.1.1

- Adds an in-app update check button and startup update check.
- Downloads new `SGManager.exe` releases to the local updates folder.
- Keeps replacement manual so the running app is not overwritten automatically.

## v0.1.0

- Initial public release channel for SGManager.
- Includes `SGManager.exe` built from the private development repository.
