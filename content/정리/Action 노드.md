Action 노드는 행동 트리에서 이동, 공격, 애니메이션 재생, 대기처럼 실제 행동을 수행하는 Leaf 노드다. 조건을 검사하는 Condition 노드와 달리 게임 상태를 직접 변경하거나 여러 프레임에 걸친 작업을 진행한다.

## 반환 상태

- `Running`: 행동이 아직 진행 중이다.
- `Success`: 행동의 목표를 정상적으로 완료했다.
- `Failure`: 행동을 수행할 수 없거나 목표 달성에 실패했다.

```csharp
public NodeState Tick()
{
    if (!hasTarget)
        return NodeState.Failure;

    agent.SetDestination(target.position);

    if (agent.pathPending || agent.remainingDistance > agent.stoppingDistance)
        return NodeState.Running;

    return NodeState.Success;
}
```

## 구현 시 주의점

행동 트리는 노드를 반복해서 Tick하므로 매 호출마다 이동을 처음부터 시작하거나 애니메이션을 재생하지 않도록 내부 상태를 관리해야 한다. 노드가 중단될 수 있다면 이동 취소, 애니메이션 정리처럼 실행 중인 작업을 종료하는 로직도 제공하는 것이 좋다.
