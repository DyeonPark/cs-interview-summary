# Map
Data Structure 다섯 번째 스터디 : 맵 (Map)

## Map
* **Key와 Value**를 가진 집합
* 중복을 허용하지 않음 (1개의 key - 1개의 value)
* Map 컬렉션에 여러 종류의 클래스가 있는데, 그중 가장 많이 사용되는 것이** HashMap, TreeMap, LinkedHashMap**

### 1. HashMap
* HashMap <K, V> → 내부적으로 array 형태로 저장 → 검색속도 매우 빠름
* 맵의 순서를 보증하지 않음 (내부 Hash 값에 따라 키순서가 정해져서, 규칙 X)
* 비동기 클래스
* NULL값을 허용

| 비교사항 | Hash Table | Hash Map |
|--|--|--|
| 병렬처리 | 권장 | 비권장 |
| 동기화 | 지원 | 미지원 |
| 속도 | 비교적 느림 | 비교적 빠름 |
| Null | 비허용 | 허용 |

### 2. TreeMap
* TreeMap <K, V> → 내부적으로 [**이진 검색 트리(Binary Search Tree)**](https://github.com/DyeonPark/cs-interview-summary/blob/master/Data%20Structrue/%5Bdongyeon%5D%20Binary%20Search%20Tree.md)의 형태로 저장
* JDK 1.2부터 제공된 TreeMap 클래스는 이진 검색 트리의 성능을 향상시킨 **레드-블랙 트리(Red-Balck Tree)**로 구현
* Map 인터페이스를 구현하므로 중복된 Key로는 값 저장 X → 같은 값을 다른 키로 저장하는 것은 가능

### 3. LinkedHashMap
* 큰 흐름에서는 위 1번의 HashMp과 동일! Entry<K, V>
* 그러나 내부적으로 **연결리스트**를 사용하였기 때문에, **입력된 순서**를 기억할 수 특징이 있음
* Entry 내에 앞/뒤 엔트리를 가리키는 before, after 속성이 있음

## HashMap vs TreeMap
| 비교사항 | HashMap | TreeMap |
|--|--|--|
| 순서 | X | 대소값순서 |
| 내부구현 | Hashing | Red-Black Tree |
| Null Key | 1개 | 불가능 |
| Null Value | 여러개 | 여러개 |
| 검색 | O(1) | O(logN) |
| 성능시간 | 매우빠름 | 비교적 느림 |
| 비교메소드 | equals() | compareTo() |
| 인터페이스 | Map | NavigableMap


## 결론
* 일반적인 경우에는 검색 성능 O(1) 이 좋은 **HashMap** 사용 ! 
* 키값이 일정한 수준대로 반복하려고 한다면, 즉 비교 연산을 사용한 순서를 보장하려고 한다면 **TreeMap** 사용
	* 그러나 TreeMap은 랜덤 접근에 대해서는 O(logN)이므로 데이터 많은 경우에는 권장 X
* 입력 순서가 의미있는 경우에는 **LinkedHashMap** 사용 권장
	* 그러나 LinkedHashMap은 랜덤접근에 O(n) 성능을 지니므로 데이터가 많은 경우에는 권장 X


## 참고문헌
* https://gbsb.tistory.com/364
* https://rangken.github.io/blog/2015/java.map/
* https://tomining.tistory.com/168
* https://genie247.tistory.com/11
