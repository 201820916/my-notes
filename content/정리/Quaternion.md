3D 회전을 표현하는 자료형. 오일러 각보다 회전 꼬임 문제가 적다.

## 코드 예시

```csharp
transform.rotation = Quaternion.Euler(0f, 90f, 0f);
```

## 이해를 돕는 설명

내부 값을 직접 수정하기보다 Euler, LookRotation, Slerp 같은 함수를 사용한다. 회전을 부드럽게 보간하고 여러 축 회전을 안정적으로 합칠 때 유리하다.
