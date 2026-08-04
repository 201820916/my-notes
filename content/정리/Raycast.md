한 방향으로 보이지 않는 광선을 쏴서 충돌 대상을 검사하는 기능.

## 코드 예시

```csharp
if (Physics.Raycast(transform.position, transform.forward, out RaycastHit hit, 5f))
    Debug.Log(hit.collider.name);
```

## 이해를 돕는 설명

총알 명중, 바닥 검사, 시야 판정처럼 선상의 첫 충돌을 찾는다. LayerMask와 최대 거리를 제한하면 불필요한 검사와 오탐을 줄일 수 있다.
