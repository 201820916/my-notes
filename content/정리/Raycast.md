한 방향으로 보이지 않는 광선을 쏴서 충돌 대상을 검사하는 기능.

## 코드 예시

```csharp
if (Physics.Raycast(transform.position, transform.forward, out RaycastHit hit, 5f))
    Debug.Log(hit.collider.name);
```

## 이해를 돕는 설명

총알 명중, 바닥 검사, 시야 판정처럼 선상의 첫 충돌을 찾는다. LayerMask와 최대 거리를 제한하면 불필요한 검사와 오탐을 줄일 수 있다.

## 더 깊이 이해하기

Unity에서 Raycast 기능을 사용할 때는 컴포넌트의 생명주기와 실행 시점을 먼저 확인해야 한다. Update와 FixedUpdate의 차이, 활성화 상태, 참조 유효성, 로컬·월드 좌표, 물리 엔진이 값을 갱신하는 시점에 따라 같은 코드도 결과가 달라질 수 있다. 반복 호출되는 경로에서는 검색과 할당 비용도 함께 점검한다.

## 적용할 때 확인할 점

Inspector 값과 코드의 기본값이 충돌하지 않는지 확인하고, 필요한 컴포넌트가 없을 때의 동작을 정의한다. Raycast 관련 처리가 매 프레임 실행된다면 GetComponent·Find·배열 생성 같은 반복 비용을 피하고, 객체가 비활성화되거나 파괴되는 경우에도 안전하도록 참조를 관리한다.
