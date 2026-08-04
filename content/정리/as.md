참조 타입을 안전하게 캐스팅하는 키워드. 실패하면 예외 대신 null을 반환한다.

## 코드 예시

```csharp
object value = "text";
string? text = value as string;
Console.WriteLine(text);
```

## 이해를 돕는 설명

변환 실패가 정상적인 흐름일 때 유용하며 결과가 null인지 반드시 확인해야 한다. 값 타입에는 일반적으로 사용할 수 없다.
