FSM(Finite State Machine, 유한 상태 머신)은 객체가 가질 수 있는 상태를 유한하게 정의하고, 조건에 따라 한 상태에서 다른 상태로 전환하도록 행동을 구성하는 방식이다.

## 구성 요소

- **State**: Idle, Move, Attack처럼 현재 행동을 나타낸다.
- **Transition**: 상태가 변경되는 조건과 방향이다.
- **Entry/Exit**: 상태에 진입하거나 빠져나갈 때 한 번 실행하는 처리다.
- **Update**: 해당 상태를 유지하는 동안 반복하는 행동이다.

## 간단한 예시

```csharp
public enum EnemyState { Idle, Chase, Attack }

private EnemyState state;

private void Update()
{
    switch (state)
    {
        case EnemyState.Idle:
            if (CanSeePlayer()) state = EnemyState.Chase;
            break;

        case EnemyState.Chase:
            MoveToPlayer();
            if (CanAttack()) state = EnemyState.Attack;
            break;

        case EnemyState.Attack:
            Attack();
            if (!CanAttack()) state = EnemyState.Chase;
            break;
    }
}
```

## 장점과 한계

한 시점에 실행되는 상태가 명확하여 캐릭터와 UI 흐름을 이해하기 쉽다. 하지만 상태 수가 늘고 모든 상태가 서로 전환할 수 있게 되면 전환 조건이 복잡해진다. 공통 행동은 상태 클래스나 계층형 FSM으로 분리하고, 독립적인 조건의 조합이 많다면 행동 트리 같은 다른 구조도 고려한다.
