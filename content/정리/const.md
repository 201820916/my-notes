`const`는 C#에서 선언과 동시에 값이 결정되고 이후 변경할 수 없는 컴파일 타임 상수를 정의하는 키워드다.

## 사용 예시

```csharp
public const int MaxPlayerCount = 4;
private const string SaveFileName = "save.json";
```

상수는 암시적으로 `static`이므로 인스턴스를 만들지 않고 `ClassName.MaxPlayerCount`처럼 접근할 수 있다. 숫자, 문자, 문자열, 열거형, `null` 등 컴파일 시점에 확정 가능한 값에 사용한다.

## readonly와 차이

```csharp
public readonly DateTime CreatedAt = DateTime.Now;
```

`readonly` 필드는 선언부나 생성자에서 런타임 값으로 초기화할 수 있지만, `const`는 컴파일 시점 값만 사용할 수 있다.

공개 `const` 값은 이를 사용하는 다른 어셈블리의 코드에 값 자체가 포함될 수 있다. 라이브러리에서 값을 변경해도 사용하는 쪽을 다시 컴파일하지 않으면 이전 값이 남을 수 있으므로, 변경 가능성이 있는 공개 값은 `static readonly`를 고려한다.
