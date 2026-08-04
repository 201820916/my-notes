x, y 두 축으로 이루어진 2D 벡터.

## 코드 예시

```csharp
Vector2 direction = new Vector2(1f, 0f);
transform.Translate(direction * Time.deltaTime);
```

## 이해를 돕는 설명

x와 y가 위치일 수도 있고 방향이나 속도일 수도 있다. 두 점의 차이를 구해 방향을 만들 때는 필요에 따라 normalized로 길이를 1로 맞춘다.
