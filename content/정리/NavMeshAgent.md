NavMesh 위에서 목적지까지 경로를 찾아 이동하는 AI 이동 컴포넌트.

## 코드 예시

```csharp
NavMeshAgent agent = GetComponent<NavMeshAgent>();
agent.SetDestination(target.position);
```

## 이해를 돕는 설명

경로 계산과 이동을 담당하지만 공격 거리나 애니메이션은 별도 로직과 맞춰야 한다. stoppingDistance와 속도, 가속도, 회전 속도가 움직임 인상에 큰 영향을 준다.
