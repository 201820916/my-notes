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

## 더 깊이 이해하기

Unity에서 MonoBehaviour 기능을 사용할 때는 컴포넌트의 생명주기와 실행 시점을 먼저 확인해야 한다. Update와 FixedUpdate의 차이, 활성화 상태, 참조 유효성, 로컬·월드 좌표, 물리 엔진이 값을 갱신하는 시점에 따라 같은 코드도 결과가 달라질 수 있다. 반복 호출되는 경로에서는 검색과 할당 비용도 함께 점검한다.

## 적용할 때 확인할 점

Inspector 값과 코드의 기본값이 충돌하지 않는지 확인하고, 필요한 컴포넌트가 없을 때의 동작을 정의한다. MonoBehaviour 관련 처리가 매 프레임 실행된다면 GetComponent·Find·배열 생성 같은 반복 비용을 피하고, 객체가 비활성화되거나 파괴되는 경우에도 안전하도록 참조를 관리한다.
