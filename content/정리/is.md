객체가 특정 타입과 호환되는지 확인하는 키워드.

## 코드 예시

```csharp
object value = "text";
if (value is string text)
    Console.WriteLine(text.Length);
```

## 이해를 돕는 설명

타입 확인과 변수 선언을 한 번에 하는 패턴 매칭을 사용할 수 있다. 상속 구조에서 실제 타입별 행동이 자주 필요하다면 다형성으로 옮길 수 있는지도 살펴볼 만하다.
