# Data-Structure
###  1.선형구조
#### ▶연결리스트
→ 연결 리스트는 자료들을 반드시 연속적으로 배열시키지는 않는다.<br>
→ 자료 항목의 순서에 따라 노드의 포인터를 이용하여 다음 자료를 연결시킨다.<br>
→ 동적 메모리에 할당된 링크에 의해 연결된 유한 개수의 데이터 원소들<br>
##### 특징
 →링크 값을 변화시키는 것 만으로 노드의 삽입 삭제가 용이하다.<br>
 →기억공간이 연속적으로 놓여 있지 않아도 저장이 가능하다.<br>
 →연결을 위한 링크(포인터) 부분이 필요하기 때문에 순차 리스트에 비해 기억공간 이용 휴율이 좋지않다.<br>
 →연결을 위한 포인터를 찾는 시간이 필요하기 때문에 접근 속도가 느리다.<br>
 →중간 노드 연결이 끊어지면 그 다음 노드를 찾지 못한다.<br>
 →희소 행렬을 링크드 리스트로 표한하면 기억장소가 절약된다.<br>
 →트리를 표한할 때 가장 적합한 자료이다.<br>
![image](https://user-images.githubusercontent.com/123055714/226499568-4af05f11-7796-4af1-9eac-548bc294fbc1.png)<br>
linked list는 한 건물 내에서 한 회사가 임대한 사무실이 서로 떨어져 있습니다.그런데 방문자가 사무실을 찾는 방법이 좀 비효율적입니다.<br> 위의 그림에 있는 방문자가 3번째 사무실을 찾아가려면 우선 첫 번째 화살표의 사무실을 찾아가야 합니다. 이 사무실의 직원에게 다음 사무실이 어딘지 물어봅니다. 그럼 알려주는 사무실로 이동 한 후에 다시 물어봐서 그다음 사무실로 이동합니다.<br>
이렇게 물어물어 사무실을 찾아가야 하는 방식이 linked list입니다. 그래서 linked list에서는 몇 번째 엘리먼트를 찾는 것이 느립니다.
#### ▶노드
자료와 포인터를 갖고 있는 것을 노드라고 한다.<br>

#### ▶희소행렬 
희소 행렬은 요소 중 많은 항들이 0(영)으로 되어 있는 형태로 기억 장소를 절약하기 위해 링크드 리스트를 이용하여 저장한다.<br>

#### ▶스택
FILO 
![image](https://user-images.githubusercontent.com/123055714/226507266-5c0de864-f8e0-4140-a7a2-76e9e83c8900.png)<br>
스택의배열,크기,포인터 생성<br>
<br>
<br>
![image](https://user-images.githubusercontent.com/123055714/226522009-345fbd55-4853-480e-a18e-0ca615666117.png)<br>
스택이 가득차거나 스택이 하나도 없을때의 경우를 만든다<br>
<br>
<br>
![image](https://user-images.githubusercontent.com/123055714/226522794-99a1b425-bb88-4b93-8866-e37e261e7ce5.png)<br>
스택 생성
<br>
<br>
![image](https://user-images.githubusercontent.com/123055714/226522826-02f58695-7725-4f94-8b6e-042f6d50d9c4.png)<br>
스택에 x 값을 넣음
<br>
<br>
![image](https://user-images.githubusercontent.com/123055714/226522911-88482fb3-131a-4c8b-ad11-42ac8f01e668.png)<br>
스택에 있는 값을 0까지 꺼냄
<br>
<br>
![image](https://user-images.githubusercontent.com/123055714/226523041-d0addeeb-6a8b-4bc4-98e3-c9aff2663377.png)

#### ▶큐
FIFO
![image](https://user-images.githubusercontent.com/123055714/226807135-60d3f7e4-12ac-4ed9-9ffb-e93b80dd7693.png)<br>
큐의 배열,크기,처음 요소 커서,맨 끝 요소 커서, 현재 데이터의 갯수를 생성<br>
<br>
<br>
![image](https://user-images.githubusercontent.com/123055714/226807353-481b2d53-7d77-4c12-8d62-a2ca006dda01.png)<br>
큐가 가득차거나 큐가 하나도 없을때의 경우를 만든다<br>
<br>
<br>
![image](https://user-images.githubusercontent.com/123055714/226807431-1f29e89e-fe9d-4953-ba03-20d8f039c9ba.png)<br>
큐를 생성<br>
<br>
<br>
![image](https://user-images.githubusercontent.com/123055714/226807576-9a391916-f6e6-4c1a-859f-8db40c7d1ed9.png)<br>
큐에 데이터를 넣음(인큐)<br>
<br>
<br>
![image](https://user-images.githubusercontent.com/123055714/226807620-5e8ac144-b5b3-46ad-afcc-3273319f0cf7.png)<br>
큐에 데이터를 뺀다(디큐)
