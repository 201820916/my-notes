`string.Format`은 형식 문자열의 자리표시자에 값을 삽입해 새로운 문자열을 만드는 C# 메서드다. 자리표시자는 `{인덱스}` 형태이며 필요하면 정렬과 서식 지정자를 함께 사용한다.

## 기본 사용법

```csharp
string text = string.Format("HP: {0}/{1}", 50, 100);
// HP: 50/100
```

## 숫자와 날짜 형식

```csharp
string score = string.Format("점수: {0:N0}", 12500);      // 점수: 12,500
string ratio = string.Format("진행률: {0:P1}", 0.756);    // 진행률: 75.6%
string date = string.Format("{0:yyyy-MM-dd}", DateTime.Now);
```

자리표시자 번호와 전달한 인자의 순서가 맞지 않거나 존재하지 않는 인덱스를 사용하면 `FormatException`이 발생할 수 있다.

일반 코드에서는 `$"HP: {hp}/{maxHp}"` 형태의 문자열 보간이 더 읽기 쉽다. 반면 번역 문구처럼 언어마다 값의 순서가 달라질 수 있는 문자열은 번호 기반 자리표시자가 유용하다. 숫자와 날짜를 표시할 때는 현재 문화권 또는 명시한 `CultureInfo`의 영향을 고려해야 한다.
