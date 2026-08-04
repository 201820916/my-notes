이전 프레임부터 현재 프레임까지 걸린 시간.

## 코드 예시

```csharp
transform.Translate(Vector3.forward * speed * Time.deltaTime);
```

## 이해를 돕는 설명

프레임마다 이동량에 곱하면 FPS가 달라도 초당 속도를 비슷하게 유지한다. FixedUpdate의 물리 계산에서는 fixedDeltaTime과의 관계도 고려한다.
