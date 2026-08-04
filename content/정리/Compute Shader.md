
화면에 삼각형을 직접 그리는 셰이더가 아닌 **GPU로 범용 병렬 계산**을 시키는 프로그램


# 일반적인 그래픽 셰이더의 흐름

Mesh → Vertex Shader → Fragment/Pixel Shader → 화면에 그리기


# Compute Shader의 흐름

Compute Shader → GPU에서 대량 계산 → 결과를 Buffer / Texture에 저장

## 코드 예시

```hlsl
#pragma kernel CSMain

[numthreads(8, 8, 1)]
void CSMain(uint3 id : SV_DispatchThreadID)
{
    // GPU 병렬 계산
}
```

## 이해를 돕는 설명

픽셀을 그리는 대신 버퍼와 텍스처를 읽고 쓰며 파티클, 군집 시뮬레이션, 이미지 처리에 활용한다. 스레드 그룹 크기와 CPU↔GPU 데이터 전송 비용이 성능을 크게 좌우한다.
