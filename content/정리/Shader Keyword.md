
셰이더 내부 기능을 켜고 끄는 옵션 이름

- 색상&강도 조정
- 기능 사용 여부
- 텍스처 자체를 지정
- etc...


IF 하나의 셰이더가 다음 키워드를 가진다면 키워드에 따라 서로 다른 Shader Variant가 만들어짐.
- \_NORMALMAP
- \_EMISSION
- \_ALPHATEST_ON

## 코드 예시

```hlsl
#pragma shader_feature _NORMALMAP

#if defined(_NORMALMAP)
    // 노말맵을 사용하는 경로
#endif
```

## 이해를 돕는 설명

키워드는 런타임 if문과 달리 필요한 코드 조합을 별도 Variant로 컴파일할 수 있다. 키워드 조합이 늘면 빌드 시간과 메모리가 폭증할 수 있으므로 범위를 관리해야 한다.
