프리팹이나 오브젝트를 런타임에 새로 생성하는 함수.

## 코드 예시

```csharp
Instantiate(enemyPrefab, spawnPoint.position, Quaternion.identity);
```

## 이해를 돕는 설명

생성 비용과 함께 Awake, OnEnable 등이 실행된다. 총알처럼 자주 생성하는 객체는 Instantiate와 Destroy 반복보다 오브젝트 풀링이 적합하다.
