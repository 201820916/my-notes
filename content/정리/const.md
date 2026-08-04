선언과 동시에 값이 고정되는 컴파일 타임 상수.

## 코드 예시

```csharp
const float Gravity = 9.81f;
float fallSpeed = Gravity * 2f;
```

## 이해를 돕는 설명

선언한 값이 호출하는 코드에 컴파일 시점에 포함될 수 있으므로 라이브러리 간 공개 상수를 바꿀 때 재컴파일 문제가 생길 수 있다. 런타임에 정할 값에는 readonly가 더 적합하다.
