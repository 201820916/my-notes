# Vertex Layout

Mesh Vertex 하나에 들어가 있는 정보 중

- Position
- Normal
- UV
- Color
- Tangent
- etc...

등을 어떤 구조로 가지고 있는지에 대한 명시


## 예시

Character Mesh 
- Position + Normal + UV + Tangent

Particle Mesh
- Position + UV + Color 

UI Mesh 
- Position + UV + Color

## 코드 예시

```hlsl
struct Attributes
{
    float3 positionOS : POSITION;
    float2 uv : TEXCOORD0;
};
```

## 이해를 돕는 설명

셰이더가 기대하는 POSITION, NORMAL, TEXCOORD 등의 형식과 메시 데이터가 맞아야 한다. 사용하지 않는 정점 속성도 메모리 대역폭을 차지하므로 목적에 맞게 구성한다.

## 더 깊이 이해하기

렌더링에서 Vertex Layout 개념은 화면 품질뿐 아니라 CPU의 렌더링 명령 제출, GPU 연산량, 텍스처와 버퍼 메모리, 메모리 대역폭에 영향을 줄 수 있다. 같은 결과라도 해상도, 오브젝트 수, 머테리얼 수, 투명도와 오버드로우에 따라 비용이 달라지므로 Frame Debugger와 GPU Profiler로 실제 병목을 확인해야 한다.

## 적용할 때 확인할 점

품질 설정은 대표 기기에서 비교하고, Vertex Layout 기능 적용 전후의 드로우 콜, 삼각형·정점 수, 셰이더 실행 시간, VRAM 사용량을 측정한다. 에디터 화면만으로 판단하지 말고 실제 빌드와 목표 해상도에서 시각적 오류와 성능을 함께 검증한다.
