객체의 상태에 따라 행동을 분리하는 패턴.

## 코드 예시

```csharp
interface IState { void Tick(); }
IState currentState = new IdleState();
currentState.Tick();
```

## 이해를 돕는 설명

Idle, Chase, Attack의 진입·실행·종료 로직을 상태별로 나누면 거대한 조건문을 줄일 수 있다. 상태 수와 전환이 매우 많아지면 행동트리나 계층형 FSM도 고려한다.
