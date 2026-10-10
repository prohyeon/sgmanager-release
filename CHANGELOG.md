# Changelog

## v0.3.3

- STOVE 창이 최소화되거나 화면 밖에 있을 때 계산된 좌표를 클릭하지 않도록 해, PyAutoGUI fail-safe 오류(`mouse moving to a corner of the screen`)로 작업이 중단되던 문제를 수정했습니다. 키 입력·클릭 직전 마우스가 화면 모서리에 있으면 안쪽으로 옮깁니다.
- fail-safe 발생, 화면 밖 좌표 클릭 생략, 커서 이동 시 STOVE 진단 로그에 커서 위치·화면 범위·전경 창 정보를 기록합니다. STOVE 창 진단에 창 좌표와 최소화 여부를 추가했습니다.
- 딸깍 ALL에서 사용자 스크립트가 탭을 닫거나 리워드샵으로 포커스를 옮기는 순간 원래 프로필 탭을 잠시 찾지 못해 `실행 상태 불명: 원래 프로필 탭이 사라졌습니다`로 중단되던 문제를 완화했습니다. 약 3초간 다시 확인한 뒤에만 탭 소실로 판단합니다.
- SGManager 내부 버전을 0.3.3, Windows 실행 파일 버전을 0.3.3.0으로 업데이트했습니다.

## v0.3.2

- 플레이 기록 API의 밀리초 숫자 날짜를 한국 시간으로 처리해 스페셜포스 준비 중 계정 전환이 중단되던 오류를 수정했습니다. 기존 문자열 날짜도 계속 지원합니다.
- 게임출석 자동인증(BETA)에도 스페셜포스 게임 인증 및 출석 반영 확인을 추가했습니다. 스페셜포스 실험 옵션을 켜면 기존 두 게임 처리 후 함께 실행합니다.
- 딸깍(BETA)와 딸깍 ALL에서도 같은 스페셜포스 처리와 날짜 수정이 적용되는지 검증했습니다. ALL은 계정별 처리 순서를 유지하고, 스페셜포스 상태 미확인 시 다음 계정 로그인 전에 중단합니다.
- 실험 옵션 이름을 `게임출석 자동인증·딸깍에 스페셜포스 포함`으로 변경했습니다. 기본값은 꺼짐이며, 기존에 켜 둔 설정은 유지됩니다.
- 형식이 잘못된 플레이 기록은 명확한 오류로 표시하고 추가 게임 인증·실행 기록 등록을 중단합니다.
- SGManager 내부 버전을 0.3.2, Windows 실행 파일 버전을 0.3.2.0으로 업데이트했습니다.

## v0.3.1

- STOVE 로그인 계정으로 스페셜포스의 행사 기간, 누적 플레이 일수, 보상 수령 상태를 조회하는 API 검증 창을 추가했습니다.
- 게임 인증 후 출석 상태를 재조회하고, 조건이 반영되면 추가 실행 기록 등록을 생략합니다. 실행 기록 등록은 별도 테스트 버튼으로 제공합니다.
- 딸깍 BETA/ALL에 스페셜포스 준비를 포함하는 실험 옵션을 추가했습니다. 기본값은 꺼짐이며, 세션 변경이나 결과 미확인 시 다음 계정으로 넘어가지 않습니다.
- 단계별 진단 JSON을 로컬에 자동 저장합니다. 토큰과 계정 식별값은 진단 JSON에 저장하지 않습니다.
- 검증 창의 배경·글자·체크박스 색상과 버튼 배치를 앱의 어두운 테마에 맞췄습니다.
- 게임 인증 오류 95009 발생 시 최초 게임 이용 등록/약관을 직접 완료하도록 안내합니다. 약관 자동 동의는 포함되지 않습니다.
- 게임 인증 API만으로 출석이 인정되는지는 게임 실행과 분리한 추가 검증이 필요합니다. 보상 수령은 웹/사용자 스크립트에서 확인합니다.
- SGManager 내부 버전을 0.3.1, Windows 실행 파일 버전을 0.3.1.0으로 업데이트했습니다.

## v0.3.0

- public-flake 2.9.2의 MY홈 개편에 맞춰 딸깍 BETA와 딸깍 ALL의 전체 자동화 버튼 탐색을 개선했습니다.
- 현재 프로필 페이지의 버튼을 확인한 뒤 입력을 전달하며, 고정 좌표 클릭과 자동 재클릭을 제거했습니다. 버튼이 가려지거나 비활성 상태이면 원인을 표시합니다.
- 리워드샵 탭이 활성화돼도 원래 프로필 탭에서 자동화 시작·완료·오류 신호를 추적합니다. 시작 직후 빠르게 발생한 오류도 결과에 반영합니다.
- 실행 여부가 불명확하거나 실행 후 관찰이 끊긴 경우 딸깍 ALL을 중단해 다음 계정으로 전환되지 않도록 했습니다.
- 버튼 탐색 실패와 자동화 오류의 상세 원인을 최종 결과에 표시하도록 개선했습니다.
- SGManager 내부 버전을 0.3.0, Windows 실행 파일 버전을 0.3.0.0으로 업데이트했습니다.

## v0.2.5

- 딸깍 ALL에서 각 계정의 로그인 세션을 확보한 직후 STOVE 비밀번호 변경 안내 팝업을 감지하고 `90일 동안 보지 않기`를 자동으로 누르도록 개선했습니다.
- 비밀번호 변경 안내 모달을 STOVE 메인 창으로 잘못 선택해 다음 계정의 정상 종료와 로그인이 연속 실패할 수 있던 문제를 수정했습니다.
- 팝업 소유 관계와 창 크기 비율을 함께 확인하고, 창 위치와 DPI에 독립적인 상대 좌표 및 전경 창 확인 후에만 클릭하도록 안전장치를 추가했습니다.
- 여러 계정을 순차 처리할 때 계정마다 `로그인 → 세션 확보 → 팝업 처리 → 딸깍 → 플레이크 갱신` 순서를 유지하는지 회귀 테스트로 검증했습니다.
- SGManager 내부 버전과 Windows 실행 파일 버전을 0.2.5로 업데이트했습니다.

## v0.2.4

- STOVE 창이 Windows에서 15초 연속 `응답 없음` 상태로 감지되면 해당 프로세스를 강제 종료하도록 개선했습니다.
- 강제 종료 후 프로세스 종료가 확인된 경우 로그인을 처음부터 한 번 자동으로 재시도합니다.
- 일시적인 지연 뒤 STOVE가 다시 응답하면 무응답 타이머를 초기화해 불필요한 종료를 방지합니다.
- STOVE 프로세스만 감지하는지, 15초 연속 무응답과 타이머 초기화 및 1회 재시도 동작을 회귀 테스트로 검증했습니다.
- SGManager 내부 버전과 Windows 실행 파일 버전을 0.2.4로 업데이트했습니다.

## v0.2.3

- 딸깍 ALL에서 기존 STOVE를 정리하며 다음 계정으로 넘어갈 때 `STOVE/게임 강제 종료 사용` 설정이 로그인 재시도 흐름에도 적용되도록 개선했습니다.
- STOVE 메인 윈도우가 사라졌지만 프로세스가 남아 있는 상태에서 다음 계정 로그인이 `메인 윈도우를 찾을 수 없습니다` 오류로 연속 실패하는 가능성을 줄였습니다.
- 딸깍 ALL의 강제 종료 설정 전달 경로를 회귀 테스트로 검증했습니다.
- SGManager 내부 버전과 Windows 실행 파일 버전을 0.2.3으로 업데이트했습니다.

## v0.2.2

- Tampermonkey가 프로필 페이지 최초 로드에서 사용자 스크립트를 늦게 주입하거나 누락하는 경우를 보완했습니다.
- 딸깍(BETA)과 딸깍 ALL의 공통 자동화 버튼 탐색 경로에서 버튼이 보이지 않으면 3초 후 페이지를 한 번 새로고침하고 다시 탐색합니다.
- 새로고침 후에도 버튼이 없으면 기존 좌표 기반 fallback을 유지해 기존 동작과 호환되도록 했습니다.
- SGManager 내부 버전과 Windows 실행 파일 버전을 0.2.2로 업데이트했습니다.

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
