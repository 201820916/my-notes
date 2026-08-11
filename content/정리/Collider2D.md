Collider2D는 Unity의 2D 물리 시스템에서 충돌 영역을 정의하는 컴포넌트 계열이다. 3D `Collider`와 이름은 비슷하지만 서로 다른 Physics2D 엔진을 사용하므로 직접 충돌하지 않는다.

## 주요 종류

- `BoxCollider2D`, `CircleCollider2D`, `CapsuleCollider2D`
- 자유로운 외곽선을 정의하는 `PolygonCollider2D`
- 여러 경계를 하나로 결합하는 `CompositeCollider2D`
- 선 형태의 `EdgeCollider2D`

## Rigidbody2D와 이벤트

움직이는 2D 물체에는 `Rigidbody2D`를 사용한다. 일반 충돌은 `OnCollisionEnter2D`, Trigger 충돌은 `OnTriggerEnter2D`처럼 이름 끝에 `2D`가 붙은 콜백으로 처리한다.

```csharp
private void OnTriggerEnter2D(Collider2D other)
{
    if (other.CompareTag("Player"))
        Debug.Log("플레이어 진입");
}
```

복잡한 Sprite 외곽선을 그대로 사용하는 것보다 가능한 한 단순한 Collider를 조합하는 것이 좋다. Tilemap에서는 CompositeCollider2D를 활용하면 인접 타일의 중복 경계를 줄일 수 있다.
