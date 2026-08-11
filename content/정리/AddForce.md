`Rigidbody.AddForce`는 Rigidbody에 힘을 적용해 물리 법칙에 따라 속도를 변화시키는 Unity 메서드다. Transform을 직접 이동시키는 것과 달리 질량, 중력, 마찰, 충돌 반응의 영향을 받는다.

## 기본 예시

```csharp
using UnityEngine;

public class Jumper : MonoBehaviour
{
    [SerializeField] private Rigidbody body;
    [SerializeField] private float jumpImpulse = 5f;

    private void FixedUpdate()
    {
        if (Input.GetKey(KeyCode.Space))
            body.AddForce(Vector3.up * jumpImpulse, ForceMode.Impulse);
    }
}
```

## ForceMode 종류

- `Force`: 질량을 고려한 지속적인 힘이다. 보통 `FixedUpdate`마다 적용한다.
- `Acceleration`: 질량을 무시하고 지속적인 가속도를 적용한다.
- `Impulse`: 질량을 고려한 순간 충격량이다. 점프나 폭발에 적합하다.
- `VelocityChange`: 질량을 무시하고 속도를 즉시 변경한다.

## 주의점

물리 연산은 고정 시간 간격으로 수행되므로 지속적인 힘은 `FixedUpdate`에서 적용하는 것이 안정적이다. 한 번의 입력에 Impulse를 사용한다면 키를 누르고 있는 동안 매 프레임 중복 적용되지 않도록 입력 시점을 구분해야 한다.
