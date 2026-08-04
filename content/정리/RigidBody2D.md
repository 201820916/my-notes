2D 물리 엔진의 영향을 받게 하는 컴포넌트.

## 이해를 돕는 설명

3D Rigidbody와 별개의 2D 물리 시스템을 사용한다. Update에서 Transform을 직접 움직이기보다 FixedUpdate와 2D 물리 API를 사용하는 것이 안정적이다.
