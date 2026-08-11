AABB(Axis-Aligned Bounding Box) 충돌은 월드 좌표축에 평행한 사각형 또는 직육면체를 이용해 두 물체가 겹치는지 판정하는 방식이다. 박스가 회전하지 않고 항상 X, Y, Z축에 정렬되어 있어 계산이 단순하고 빠르다.

## 판정 원리

2D에서는 두 박스의 X축 구간과 Y축 구간이 모두 겹치면 충돌한 것으로 본다. 어느 한 축이라도 완전히 분리되어 있으면 충돌하지 않는다.

```csharp
bool Overlaps(Bounds a, Bounds b)
{
    return a.min.x <= b.max.x && a.max.x >= b.min.x
        && a.min.y <= b.max.y && a.max.y >= b.min.y
        && a.min.z <= b.max.z && a.max.z >= b.min.z;
}
```

## 장점과 한계

AABB는 비교 연산만으로 판정할 수 있어 많은 객체를 빠르게 검사하는 Broad Phase에 적합하다. 반면 물체가 회전해도 박스는 월드 축에 고정되므로 실제 모양보다 넓은 빈 공간을 포함할 수 있다. 이 때문에 AABB로 충돌 후보를 먼저 찾은 뒤, 실제 Collider 형태를 이용해 정밀 판정을 수행하는 방식이 자주 사용된다.

회전된 상자를 정밀하게 표현해야 한다면 OBB를 고려하지만, 축 투영과 회전 계산이 추가되어 비용이 증가한다.
