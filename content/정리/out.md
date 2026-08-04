메서드가 여러 값을 반환할 때 사용하는 참조 전달 키워드. 메서드 안에서 반드시 값을 할당해야 한다.

## 코드 예시

```csharp
bool ok = int.TryParse("42", out int value);
Console.WriteLine(value); // 42
```

## 이해를 돕는 설명

TryParse 패턴처럼 성공 여부와 결과값을 함께 돌려줄 때 자주 사용한다. C#의 튜플 반환을 쓰면 여러 결과의 이름을 더 명확하게 표현할 수도 있다.
