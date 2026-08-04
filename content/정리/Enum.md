정수 값에 이름을 붙여 의미 있게 사용하는 사용자 정의 자료형.

## 코드 예시

```csharp
enum GameState { Title, Playing, GameOver }
GameState state = GameState.Playing;
```

## 이해를 돕는 설명

숫자 0, 1, 2보다 Playing, Paused 같은 이름으로 상태를 표현해 실수를 줄인다. 저장 데이터에 정수값을 직접 기록한다면 멤버 순서 변경에 주의해야 한다.
