물리 엔진의 영향을 받게 하는 컴포넌트.

## 코드 예시

```csharp
Rigidbody rb = GetComponent<Rigidbody>();
rb.linearVelocity = Vector3.forward * 5f;
```

## 이해를 돕는 설명

Transform을 직접 바꾸면서 물리 이동을 섞으면 충돌 계산이 불안정해질 수 있다. 물리 객체는 FixedUpdate에서 velocity나 MovePosition, 힘을 통해 움직이는 방식을 선택한다.
