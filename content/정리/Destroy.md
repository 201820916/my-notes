`Destroy`는 Unity에서 `GameObject`, 컴포넌트 또는 UnityEngine.Object 기반 객체의 제거를 예약하는 메서드다.

## 사용 예시

```csharp
Destroy(gameObject);       // 현재 오브젝트 제거
Destroy(hitEffect, 2f);    // 2초 뒤 제거
Destroy(GetComponent<Rigidbody>()); // 특정 컴포넌트 제거
```

## 제거 시점

`Destroy`를 호출해도 객체는 그 코드 줄에서 즉시 메모리에서 사라지지 않는다. 실제 제거는 일반적으로 현재 Update 루프가 끝난 뒤 렌더링 전에 처리된다. 따라서 같은 프레임의 다른 코드가 제거 예정 객체를 참조할 수 있으므로 흐름을 주의해야 한다.

`DestroyImmediate`는 에디터 도구처럼 즉시 제거가 꼭 필요한 상황을 위한 API이며, 런타임에서는 반복 컬렉션과 엔진 상태를 깨뜨릴 수 있어 일반적으로 사용하지 않는다.

## 성능상 주의점

짧은 시간에 `Instantiate`와 `Destroy`를 반복하면 할당, 초기화, 가비지 컬렉션 비용이 누적될 수 있다. 총알이나 이펙트처럼 빈번하게 재사용하는 객체는 비활성화해 보관하는 오브젝트 풀링이 적합하다.
