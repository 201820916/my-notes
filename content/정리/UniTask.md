유니티에서 async/await를 효율적으로 쓰기 위한 비동기 라이브러리.

## 코드 예시

```csharp
async UniTask LoadAsync()
{
    await UniTask.Delay(1000);
}
```

## 이해를 돕는 설명

Task보다 Unity의 PlayerLoop와 메모리 특성에 맞춘 비동기 처리를 제공한다. 취소 토큰과 오브젝트 파괴 시점을 연결해 완료되지 않은 작업이 남지 않게 해야 한다.
