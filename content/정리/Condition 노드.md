Condition 노드는 행동 트리에서 현재 상태나 주변 환경을 검사하고 `Success` 또는 `Failure`를 반환하는 Leaf 노드다. 행동을 직접 수행하기보다 다음 행동을 실행해도 되는지 판단하는 질문 역할을 한다.

## 예시

```csharp
public NodeState Tick()
{
    float distance = Vector3.Distance(transform.position, target.position);
    return distance <= attackRange
        ? NodeState.Success
        : NodeState.Failure;
}
```

거리, 체력, 시야, 탄약, 쿨다운 같은 값을 검사할 수 있다. 일반적으로 상태를 변경하지 않는 순수한 판정으로 만드는 것이 결과를 예측하고 재사용하기 쉽다.

## 구현 시 주의점

Condition은 매 Tick 자주 실행될 수 있으므로 불필요한 메모리 할당이나 비싼 전체 검색을 피해야 한다. 물리 쿼리나 경로 계산이 필요하다면 검사 주기를 낮추거나 결과를 캐싱한다. 이름은 `CanAttack`, `HasTarget`처럼 참·거짓의 의미가 분명하게 작성하는 것이 좋다.
