거리에 따라 모델의 디테일을 바꾸는 최적화 기법.

## 코드 예시

```csharp
LODGroup lodGroup = GetComponent<LODGroup>();
lodGroup.RecalculateBounds();
```

## 이해를 돕는 설명

화면에서 차지하는 크기가 작아질수록 단순한 모델을 사용한다. 단계 전환이 눈에 띄지 않게 임계값과 크로스페이드를 조정하고 실제 삼각형 감소량도 확인한다.
