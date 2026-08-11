Collider는 Unity의 3D 물리 시스템에서 오브젝트의 충돌 영역을 정의하는 컴포넌트다. 화면에 보이는 Mesh와 충돌 모양은 서로 독립적이며, Collider 자체가 물체를 움직이지는 않는다.

## 주요 종류

- `BoxCollider`: 상자 형태로 계산이 단순하다.
- `SphereCollider`: 구 형태로 회전의 영향을 받지 않는다.
- `CapsuleCollider`: 캐릭터처럼 길쭉한 물체에 적합하다.
- `MeshCollider`: Mesh 형태를 사용해 정밀하지만 계산 비용이 높다.

## Rigidbody와의 관계

움직이며 물리 반응을 해야 하는 오브젝트에는 보통 Rigidbody가 필요하다. Collider만 있는 오브젝트는 정적인 충돌체로 취급된다. 두 Collider의 충돌 이벤트를 안정적으로 받으려면 일반적으로 둘 중 하나 이상에 Rigidbody가 있어야 한다.

## Trigger

`Is Trigger`를 활성화하면 물리적으로 밀어내지 않고 겹침 여부만 감지하며 `OnTriggerEnter`, `OnTriggerStay`, `OnTriggerExit`를 사용한다.

움직이는 오브젝트에는 단순한 기본 Collider 조합을 우선 사용한다. 비볼록 MeshCollider는 동적 Rigidbody와 함께 사용할 수 없거나 제약이 크므로 용도와 성능을 확인해야 한다.
