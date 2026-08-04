움직이는 장애물이나 문처럼 길을 막는 대상을 AI가 피하도록 만드는 컴포넌트.

## 코드 예시

```csharp
GetComponent<NavMeshObstacle>().carving = true;
```

## 이해를 돕는 설명

정적인 장애물은 베이크에 포함하는 편이 저렴하고, 움직이거나 상태가 바뀌는 장애물에 사용한다. Carving을 너무 자주 갱신하면 NavMesh 재계산 비용이 커질 수 있다.
