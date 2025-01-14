# Array & List

배열(Array)과 리스트(List)는 매우 유사한 자료구조이다. 언어마다 기본적으로 배열과 리스트를 내장하는지 여부와 그 특성에 차이가 있어서 더욱 모호하게 다루어지곤 한다. 자료구조 배열과 리스트의 특성을 알아본다.

<br/>

## 배열(Array)

[**배열(Array)**](https://github.com/da-in/tech-interview-study/blob/main/Data%20Structure/Array.md) 은 일반적으로 같은 종류의 데이터들이 순차적으로 저장되어있는 자료구조이다.

- 연속적인 메모리 공간에 저장되어 논리적 저장 순서와 물리적 저장 순서가 같기 때문에, 인덱스(Index)를 통해서 데이터에 바로 접근할 수 있다. 따라서 Array 에서 인덱스는 주소에 상응하는 의미를 갖게 된다.
- 물리적 메모리와 인덱스가 고정되어있으므로, 특정 인덱스의 데이터를 삭제해도 인덱스와 빈 공간이 남는다. 이는 메모리 측면에서 비효율적이다.
- 고정된 크기를 갖는다.
- 캐시 메모리 적중률이 낮다.
- 삽입, 삭제의 시간복잡도 `O(N)`. 삽입과 삭제시 해당 인덱스 주변의 값을 이동시키는 과정이 필요하기 때문이다.
- 접근 시간복잡도 `O(1)`

<br/>

## 리스트(List)

리스트(List) 역시 순서를 갖는 데이터들의 집합인 선형자료구조로, 시퀀스(Sequence)라고도 한다.

- 리스트는 메모리 공간에 비연속적으로 데이터를 저장하고 포인터로 다음 데이터를 가리킨다. 따라서 낭비되는 메모리가 없다.
- 포인터를 저장할 공간이 필요하고, 그렇기에 배열보다 구조가 복잡하다.
- 비연속적으로 저장되기에 인덱스로는 해당 데이터에 바로 접근할 수 없다. 인덱스는 단순히 데이터의 순서 정도의 의미만 갖게된다.
- 크기가 고정되어있지 않다.
- 캐시 메모리 적중률이 낮다.
- 삽입, 삭제의 시간복잡도 `O(1)`
- 접근 시간복잡도 `O(N)`. 주소를 가리키는 인덱스가 없어 Head 포인터부터 순서대로 접근해야한다.

<br/>

![array-vs-ll](https://user-images.githubusercontent.com/66757141/212114948-d0b2142b-b4d9-4e3e-82e9-913bbdc0ff24.png)<br/>
_[image reference](https://www.interviewbit.com/courses/programming/linked-lists/arrays-vs-linked-lists/)_

<br/>

## 캐시 메모리 적중률(Cache Hit Ratio)

**캐시 메모리** 는 CPU와 메모리의 속도 차이를 줄이기 위해 사용하는 고속 버퍼 메모리이다. 자주 사용하는 데이터를 캐시 메모리에 저장하여 빠르게 꺼내써, 메모리 접근 횟수를 줄이고 성능을 향상시킨다._(빠르고 비싸다)_

CPU가 메모리에 접근하기 전 캐시 메모리에 필요한 데이터의 존재 여부를 확인한다. 데이터가 있는 경우를 `적중(hit)`, 없는 경우를 `실패(miss)`라고 한다.

**적중률(Hit Ratio)** 는 요청한 데이터를 캐시메모리에서 찾을 확률이다.

$ratio = \frac {hits} {hits + miss}$

캐시 메모리는 참조의 지역성(Lacality)에 근거한다.

- `시간적 지역성(temporal Locality)` : 한 번 참조한 데이터이터를 다시 참조할 가능성이 높다.
- `공간적 지역성(spatial Locality)` : 참조한 데이터와 인접한 데이터가 참조될 가능성이 높다.
- `순차적 지역성(sequential Locality)` : 분기가 발생하지 않는 한 메모리에 저장된 순서대로 실행된다.

Array는 연속적인 메모리에 데이터를 저장하고, List는 비연속적인 메모리에 저장한다는 점에서 공간적 지역성 측면에서 Array의 캐시 메모리 적중률이 더 높을 것이다.

<br/>

## List(Python)

다른 언어에서는 배열과 리스트가 비교적 명확하게 구분되어 사용된다. 하지만 파이썬(Python)의 리스트는 배열의 특성도 함께 내포하여 구현되어있다. 파이썬의 리스트는 연속적인 메모리 공간에 데이터를 저장하고, 인덱스로 접근할 수 있다.

<br/>

## Array List (Java)

Java의 `java.util` 패키지는 크기가 조정가능한 Array인 ArrayList 클래스를 제공한다. ArrayList는 저장 가능한 용량(Capacity)와 현재 사용중인 용량(Size)가 있고, 가능한 용량 이상을 사용하려고 하면 더 큰 공간의 메모리를 새로 할당한다.

<br/>

---

## Reference

📄https://ko.wikipedia.org/wiki/배열  
📄https://opentutorials.org/module/1335/8636  
📄https://ongveloper.tistory.com/403  
📄https://ndlessrain.tistory.com/entry/캐시메모리-적중률Hit-Rate
📄https://zion830.tistory.com/46  
📄https://www.w3schools.com/java/java_arraylist.asp
