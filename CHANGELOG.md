# Changelog

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
