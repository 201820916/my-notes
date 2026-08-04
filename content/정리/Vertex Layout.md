
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
