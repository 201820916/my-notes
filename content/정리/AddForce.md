Rigidbody에 힘을 가해 움직이게 하는 함수.

## 코드 예시

```csharp
GetComponent<Rigidbody>().AddForce(Vector3.up * 5f, ForceMode.Impulse);
```

## 이해를 돕는 설명

ForceMode에 따라 지속적인 힘, 순간 충격, 질량 무시 등 결과가 달라진다. 점프처럼 즉각적인 변화에는 Impulse가 자주 쓰인다.
