Enum(열거형)은 관련된 정수 상수 집합에 의미 있는 이름을 부여하는 C# 값 타입이다. 숫자를 직접 사용하는 것보다 가능한 상태와 의도를 명확하게 표현할 수 있다.

## 기본 사용법

```csharp
public enum GameState
{
    Title = 0,
    Playing = 1,
    Paused = 2,
    GameOver = 3
}

GameState state = GameState.Playing;
```

## Flags 열거형

여러 값을 동시에 조합해야 한다면 비트 플래그를 사용할 수 있다.

```csharp
[Flags]
public enum DamageType
{
    None = 0,
    Fire = 1 << 0,
    Ice = 1 << 1,
    Poison = 1 << 2
}
```

저장 파일이나 네트워크 데이터에 Enum의 정수값을 기록한다면 멤버 순서를 바꾸거나 중간에 새 값을 삽입할 때 기존 데이터의 의미가 달라질 수 있다. 이런 경우 각 값을 명시적으로 지정하고 삭제된 값도 호환성을 고려해 관리해야 한다.
