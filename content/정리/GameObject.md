유니티 씬에 존재하는 기본 객체 단위. 실제 기능은 컴포넌트를 붙여 구성한다.

## 코드 예시

```csharp
GameObject player = GameObject.FindWithTag("Player");
player.SetActive(true);
```

## 이해를 돕는 설명

Transform은 항상 포함되며 그 자체에는 이동이나 표시 기능이 없다. Renderer, Collider, 사용자 스크립트 같은 컴포넌트를 붙여 실제 동작을 만든다.
