Addressables는 Unity 에셋을 직접 참조 대신 주소로 식별하여 비동기로 로드하고, 로컬 또는 원격 번들로 배포할 수 있게 해 주는 리소스 관리 시스템이다.

## 주요 개념

- **Address**: 에셋을 찾는 문자열 식별자다.
- **Group**: 에셋을 빌드하고 배포할 단위다.
- **Catalog**: 주소와 실제 번들의 위치를 연결하는 목록이다.
- **Handle**: 비동기 작업의 상태와 로드된 결과를 보관한다.

## 로드와 해제

```csharp
using UnityEngine;
using UnityEngine.AddressableAssets;
using UnityEngine.ResourceManagement.AsyncOperations;

public class IconLoader : MonoBehaviour
{
    private AsyncOperationHandle<Sprite> handle;

    public async void Load()
    {
        handle = Addressables.LoadAssetAsync<Sprite>("ui/icon_sword");
        Sprite icon = await handle.Task;
    }

    private void OnDestroy()
    {
        if (handle.IsValid())
            Addressables.Release(handle);
    }
}
```

## 장점과 주의점

필요한 시점에만 에셋을 로드하고 원격 콘텐츠를 별도로 갱신할 수 있다. 하지만 Addressable로 표시하는 것만으로 메모리가 자동 관리되는 것은 아니다. 로드 횟수와 해제 시점을 대응시키고, 인스턴스 생성에는 `ReleaseInstance` 등 API에 맞는 해제 방식을 사용해야 한다.
