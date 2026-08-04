자식 클래스에서 부모 클래스의 멤버나 생성자를 명시적으로 참조하는 키워드.

## 코드 예시

```csharp
class Enemy { protected int hp = 10; }
class Boss : Enemy
{
    void PrintHp() => Console.WriteLine(base.hp);
}
```

## 이해를 돕는 설명

부모의 초기화나 기본 동작을 유지하면서 자식 기능을 덧붙일 때 쓴다. 부모 구현을 호출해야 하는 라이프 사이클 메서드에서는 누락 여부를 확인해야 한다.
