오브젝트를 지정한 각도만큼 회전시키는 함수.

## 코드 예시

```csharp
transform.Rotate(0f, 90f * Time.deltaTime, 0f);
```

## 이해를 돕는 설명

오일러 각을 매 프레임 더하는 간단한 회전에 편리하다. 정확한 목표 방향이나 보간에는 Quaternion 기반 함수가 더 적합하다.
