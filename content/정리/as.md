`as`는 C#에서 객체를 지정한 참조 타입으로 안전하게 변환하는 연산자다. 변환할 수 없으면 예외를 발생시키지 않고 `null`을 반환한다.

## 사용 예시

```csharp
object value = "hello";
string text = value as string;

if (text != null)
    Console.WriteLine(text.Length);
```

직접 캐스팅인 `(string)value`는 변환할 수 없을 때 `InvalidCastException`을 발생시키지만, `as`는 실패를 정상적인 분기로 처리할 수 있다.

## 패턴 매칭과 비교

타입 검사와 변수 선언을 동시에 해야 한다면 패턴 매칭이 더 간결하다.

```csharp
if (value is string message)
    Console.WriteLine(message);
```

`as`는 참조 타입과 Nullable 값 타입에 사용할 수 있다. 결과가 `null`일 수 있으므로 반드시 확인해야 하며, 변환 실패가 프로그램 오류여야 하는 상황에서는 명시적 캐스팅이 의도를 더 잘 드러낼 수 있다.
