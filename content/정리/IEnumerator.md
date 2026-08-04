C#에서 순차적으로 값을 반환하거나 유니티 코루틴을 구성할 때 사용하는 인터페이스.

## 코드 예시

```csharp
IEnumerator WaitThenPrint()
{
    yield return new WaitForSeconds(1f);
    Debug.Log("Done");
}
```

## 이해를 돕는 설명

일반 C#에서는 열거 동작을 표현하고 Unity에서는 yield 지점을 기준으로 실행을 나누는 코루틴에 사용된다. 반환형이 IEnumerator라고 해서 자동으로 실행되는 것은 아니며 StartCoroutine이 필요하다.
