# iOS 앱 생명주기

## 앱 생명주기
앱 생명주기란 앱의 실행부터 종료까지의 프로세스의 상태 변화의 흐름을 의미한다.

## 앱의 실행 영역

> Foreground 와 Background의 공통점은 둘 다 메모리가 올라가 있다는 점이다.

- Foreground : 사용자에게 직접 UI가 표시되며 입력을 받아 앱과 상호작용 할 수 있는 상태를 의미한다.
  
- Background : 사용자에게 보이지 않으며, 앱이 화면에 표시되지 않은 상태로 제한된 작업만 수행할 수 있는 상태를 의미한다.
  
***

## 앱의 상태

- Not running : 아직 메모리가 올라가 있지 않으며 OS에 의해 서비스가 완전히 종료된 상태이다.사용자와 이벤트를 수신하고 있지 않는다. (앱이 실행되지 않은 상태.)
  
- Foreground - Inactive : 앱이 화면을 점유하지만 사용자와 상호작용할 수 없거나 모든 동작을 제어할 수 없는 상태이다. (전화나 알람 등으로 인해 앱이 잠시 비활성화 상태로 진입한다.)
  
- Foreground - Active :앱이 화면을 점유하며 Inactive와 달리 사용자의 모든 이벤트를 받아 상호작용할 수 있는 상태이다. (무조건 Inactive 상태를 통해 진입한다.)
  
- Background - Running :앱이 Background 상태에 있으나 실행되는 코드가 있고 리소스와 데이터를 계속 소모하고 있는 상태이다. (Forgerground 상태에서 홈화면으로 나가는 경우나 다른 앱으로 전환하는 경우에 진입한다.)

- Background - Suspended :앱이 Background 상태에 있지만 코드를 실행시키지 않은 상태이다. 앱을 다시 실행했을 때 최근 작업을 빠르게 로드하기 위해 메모리에 최소한의 데이터만 저장되어 있다. (Running 상태에서 다른 작업을 하고 있지 않으면 진입한다.)
  
  ***

## 앱의 상태 변화와 흐름

1. **Not Running → Foreground - Inactive**  
   - 사용자가 앱을 실행하면 시스템이 앱을 메모리에 올리고, 앱은 Inactive 상태로 진입한다.

2. **Foreground - Inactive → Foreground - Active**  
   - 앱이 초기화 작업을 마치고 사용자와 상호작용할 준비가 되면 Active 상태로 전환된다.

3. **Foreground - Active → Foreground - Inactive**  
   - 전화 수신, 알림 등 시스템 인터럽트로 인해 일시적으로 Inactive 상태로 진입할 수 있다.

4. **Foreground - Inactive → Background - Running**  
   - 사용자가 홈 버튼을 누르거나 다른 앱으로 전환하면 앱은 Background 상태로 진입하고, 코드 실행이 계속된다.

5. **Background - Running → Background - Suspended**  
   - 일정 시간 동안 코드 실행이 없으면 시스템이 앱을 Suspended 상태로 전환한다.  
   - 이때 앱은 메모리에 존재하지만 코드 실행은 멈춘다.

6. **Background - Suspended → Foreground - Inactive**  
   - 사용자가 앱을 다시 실행하면 Suspended 상태에서 Inactive 상태로 복귀한다.  
   - 앱이 메모리에 남아있기 때문에 빠르게 복귀할 수 있다.

7. **Foreground - Inactive → Foreground - Active**  
   - 앱이 다시 사용자와 상호작용할 준비가 되면 Active 상태로 전환된다.

8. **(어느 상태에서든) → Not Running**  
   - 사용자가 앱을 종료하거나, 시스템이 메모리 확보 등의 이유로 앱을 강제 종료하면 Not Running 상태로 진입한다.
