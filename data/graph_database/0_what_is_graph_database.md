## Graph Database

### 특징
- 데이터가 RDB, NoSQL과는 다르게 도메인의 개념적인 모델을 더 잘 표현한다
- 데이터를 저장할 때 개념적 연관성을 함께 저장한다
- 마인드맵과 같은 형태로 표현하기 쉬워서 whiteboard-friendly

### Storing
- A 테이블, B 테이블에 데이터를 입력하고 관계에 대한 정보를 메모리 포인터에 저장하는 것과 같다
  - B 테이블의 해당 데이터를 조회할 때마다 엮여있는 A 테이블의 데이터를 조회한다
  - join과 비슷한 결과 도출
  - RDB에서는 FK, 중간테이블을 통해 물리적인 연결을 맺고있고, 연관된 데이터가 있는지 확인하기 위해서는 query를 통해서 반환 결과를 확인하여야한다.

### Select
- Person, Company 노드가 있고, WORKS_FOR의 관계가 있다고 가정
  - 특정 사람이 근무하고 있는 회사를 찾고 싶을 때 Person node에서 WORKS_FOR의 관계를 맺고 있는 노드를 찾으면 된다
  - 도메인과의 연관성이 잘 그려지고 이해하기 쉽다고 생각한다.

### Examplia
```MATCH (p:Person {lastName: 'Reif'})-[r:WORKS_FOR]->(c:Company)
RETURN p, r, c```
