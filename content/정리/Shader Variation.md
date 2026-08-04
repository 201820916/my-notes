
같은 셰이더에서 옵션 조합이 달라져 만들어진 서로 다른 실행 버전



| Variant | 활성 Keyword  | 동작       |
| ------- | ----------- | -------- |
| A       | 없음          | 기본 조명    |
| B       | \_NORMALMAP | 노멀맵      |
| C       | \_EMISSION  | 발광       |
| D       | 둘 다         | 노멀맵 + 발광 |

## 코드 예시

```hlsl
#pragma multi_compile _ _EMISSION

#if defined(_EMISSION)
    color += emissionColor;
#endif
```

## 이해를 돕는 설명

키워드와 품질 설정 조합마다 실행 코드가 달라진 결과다. 실제 빌드에서 사용하지 않는 Variant를 제거하지 않으면 셰이더 빌드와 로딩이 느려질 수 있다.
