오브젝트의 위치, 회전, 크기를 담당하는 컴포넌트.

## 코드 예시

```csharp
transform.position += Vector3.right * Time.deltaTime;
```

## 이해를 돕는 설명

부모가 움직이거나 회전하면 자식의 월드 Transform도 영향을 받는다. position과 localPosition, rotation과 localRotation을 상황에 맞게 구분한다.
