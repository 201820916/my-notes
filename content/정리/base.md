`base`는 C#의 파생 클래스에서 부모 클래스의 생성자, 메서드, 프로퍼티 또는 필드에 접근할 때 사용하는 키워드다. 자식 클래스가 같은 이름의 멤버를 재정의했더라도 부모 구현을 명시적으로 선택할 수 있다.

## 부모 생성자 호출

```csharp
class Enemy
{
    protected int hp;

    public Enemy(int hp)
    {
        this.hp = hp;
    }
}

class Boss : Enemy
{
    public Boss() : base(500)
    {
    }
}
```

## 부모 메서드 확장

```csharp
class Boss : Enemy
{
    public override void TakeDamage(int amount)
    {
        base.TakeDamage(amount);
        PlayHitEffect();
    }
}
```

부모 동작을 유지하면서 자식 기능을 덧붙일 때 유용하다. 다만 부모 구현을 반드시 호출해야 하는 구조가 많아지면 클래스 간 결합도가 높아질 수 있다. 어떤 초기화와 부수 효과가 부모 메서드에 포함되어 있는지 확인해야 한다.
