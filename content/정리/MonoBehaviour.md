유니티 스크립트가 컴포넌트로 동작하게 해주는 기본 클래스.

## 코드 예시

```csharp
public class PlayerMover : MonoBehaviour
{
    void Update() { }
}
```

## 이해를 돕는 설명

new로 직접 생성하는 일반 클래스가 아니라 GameObject에 붙여 엔진이 관리한다. 생성자보다 Awake와 Start를 초기화 지점으로 사용한다.
