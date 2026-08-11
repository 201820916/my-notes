Compute Shader는 화면에 삼각형을 직접 그리는 대신 GPU의 대규모 병렬 연산 기능을 범용 계산에 사용하는 셰이더 프로그램이다. 결과는 Buffer나 Texture에 저장하며 파티클, 군집 시뮬레이션, 이미지 처리, 절차적 생성 등에 활용한다.

## HLSL 커널

```hlsl
#pragma kernel CSMain

RWTexture2D<float4> Result;

[numthreads(8, 8, 1)]
void CSMain(uint3 id : SV_DispatchThreadID)
{
    Result[id.xy] = float4(id.x / 256.0, id.y / 256.0, 0, 1);
}
```

`numthreads`는 하나의 스레드 그룹에 포함되는 스레드 수를 정의한다. `SV_DispatchThreadID`는 전체 실행 범위에서 각 스레드의 고유 인덱스를 제공한다.

## Unity에서 실행

```csharp
int kernel = shader.FindKernel("CSMain");
shader.SetTexture(kernel, "Result", resultTexture);
shader.Dispatch(kernel, 32, 32, 1); // 8×8 그룹으로 256×256 처리
```

## 성능상 주의점

GPU는 동일한 연산을 많은 데이터에 적용할 때 강하지만, 분기가 심하거나 데이터가 적으면 이점이 줄어든다. CPU와 GPU 사이의 데이터 전송과 결과 읽기(Readback)는 동기화를 일으킬 수 있으므로 최소화해야 한다. 스레드 그룹 크기는 대상 플랫폼의 GPU 특성과 처리 크기에 맞춰 프로파일링한다.
