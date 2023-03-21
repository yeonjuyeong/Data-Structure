# Data-Structure
### 1.선형구조
#### 연결리스트
연결 리스트는 자료들을 반드시 연속적으로 배열시키지는 않는다.<br>
자료 항목의 순서에 따라 노드의 포인터를 이용하여 다음 자료를 연결시킨다.<br>
동적 메모리에 할당된 링크에 의해 연결된 유한 개수의 데이터 원소들<br>
##### 특징
링크 값을 변화시키는 것 만으로 노드의 삽입 삭제가 용이하다.<br>
기억공간이 연속적으로 놓여 있지 않아도 저장이 가능하다.<br>
연결을 위한 링크(포인터) 부분이 필요하기 때문에 순차 리스트에 비해 기억공간 이용 휴율이 좋지않다.<br>
연결을 위한 포인터를 찾는 시간이 필요하기 때문에 접근 속도가 느리다.<br>
중간 노드 연결이 끊어지면 그 다음 노드를 찾지 못한다.<br>
희소 행렬을 링크드 리스트로 표한하면 기억장소가 절약된다.<br>
트리를 표한할 때 가장 적합한 자료이다.<br>

#### 노드
자료와 포인터를 갖고 있는 것을 노드라고 한다.<br>

#### 희소행렬 
희소 행렬은 요소 중 많은 항들이 0(영)으로 되어 있는 형태로 기억 장소를 절약하기 위해 링크드 리스트를 이용하여 저장한다.<br>
