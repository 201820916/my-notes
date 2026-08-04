C#의 모든 타입이 기본적으로 상속받는 최상위 타입.

## 코드 예시

```csharp
object value = "hello";
Console.WriteLine(value.GetType()); // System.String
```

## 이해를 돕는 설명

값 타입도 object로 다룰 수 있지만 이 과정에서 박싱이 생길 수 있다. Equals, GetHashCode, ToString 같은 기본 동작은 모든 C# 타입에서 출발점이 된다.
