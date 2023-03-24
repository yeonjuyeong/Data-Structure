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
스택은 리스트의 한쪽 끝으로만 자료의 삽입 및 삭제가 이루어지는 구조로 먼저 삽입된 자료가 맨 나중에 삭제가 되는 후입선출(LIFO)방식이다.
###### 삽입
![image](https://user-images.githubusercontent.com/123055714/226809476-62237adf-0075-4b32-b176-4dff70eef938.png)
###### 삭제
![image](https://user-images.githubusercontent.com/123055714/226809731-8f4242ed-ad39-4352-9c06-2a28eb1a70e5.png)
#### java로 구현
```java
public class IntStack {
	private int[] stk;	//스택용 배열
	private int capacity;	//스택의 크기
	private int ptr;	//스택용 포인터
```
스택의배열,크기,포인터 생성<br>
<br>
<br>
```java
	//--- 실행시 예외: 스택이 비어있음 ---//
	public class EmptyIntStackException extends RuntimeException{
		public EmptyIntStackException() { }
	}
	//--- 실행시 예외: 스택이 가득 참 ---//
		public class OverflowIntStackException extends RuntimeException{
			public OverflowIntStackException() { }
	}
```
스택이 가득차거나 스택이 하나도 없을때의 경우를 만든다<br>
<br>
<br>
```java
		//--- 생성자(constructor) ---//
		public IntStack(int maxlen) {
			ptr = 0;
			capacity = maxlen;
			try {
				stk = new int[capacity];	//스택 본체용 배열을 생성
			}catch(OutOfMemoryError e) {	//생성할 수 없음
				capacity = 0;
			}
		}
 ```
스택 생성
<br>
<br>
```java
		//--- 스택에 x를 푸시 ---//
		public int push(int x)throws OverflowIntStackException{
			if(ptr>= capacity)		//스택이 가득 참
				throw new OverflowIntStackException();
			return stk[ptr++] = x;
		}
  ```
스택에 x 값을 넣음
<br>
<br>
```java
		//--- 스택에서 데이터를 팝(정상에 있는 데이터를 꺼냄) ---//
		public int pop() throws EmptyIntStackException{
			if(ptr == 0)			//스택이 빔
				throw new EmptyIntStackException();
			return stk[--ptr];
		}
  ```
스택에 있는 값을 0까지 꺼냄
<br>
<br>
![image](https://user-images.githubusercontent.com/123055714/226808772-74dfacac-df3c-494f-a395-dc111478ecee.png)





#### ▶큐
큐는 한쪽 방향으로 데이터가 삽입되고 반대 방향으로 데이터가 삭제되는 구조로 먼저 들어온 데이터가 먼저 나가는 선입선출(FIFO)방식이다.
###### 삽입,
![image](https://user-images.githubusercontent.com/123055714/226809976-18c436d7-019b-48a9-97c6-a2f87a44442b.png)
#### java로 구현
```java
public class IntQueue {                  
	private int[] que;		//큐용 배열      
	private int capacity;		//큐의 크기  
	private int front;		//맨 처음 요소 커서 
	private int rear;		//맨 끝 요소 커서  
	private int num;		//현재 데이터 개수  
```
큐의 배열,크기,처음 요소 커서,맨 끝 요소 커서, 현재 데이터의 갯수를 생성<br>
<br>
<br>
```java
//--- 실행시 예외: 큐가 비어있음 ---//                                       
public class EmptyIntQueueException extends RuntimeException{     
	public EmptyIntQueueException() { }                           
}                                                                 
//--- 실행시 예외: 큐가 가득 찼음 ---//                                      
public class OverflowIntQueueException extends RuntimeException{  
	public OverflowIntQueueException() { }                        
 }
```
큐가 가득차거나 큐가 하나도 없을때의 경우를 만든다<br>
<br>
<br>
```java
//--- 생성자(constructor) ---//                         
public IntQueue(int maxlen) {                        
	num = front = rear = 0;                          
	capacity = maxlen;                               
	try {                                            
		que = new int[capacity];	//큐 본체용 배열 생성    
	}catch (OutOfMemoryError e) {	//생성할 수 없음       
		capacity = 0;                                
	}                                                
}
```
큐를 생성<br>
<br>
<br>
```java
//--- 큐에 데이터를 인큐 ---//                                   
public int enque(int x) throws OverflowIntQueueException{
	if(num >= capacity)                                  
		throw new OverflowIntQueueException();           
	que[rear++]	 = x;                                    
	num++;                                               
	if(rear == capacity)                                 
	rear = 0;                                            
	return x;                                            
}                     
```
큐에 데이터를 넣음(인큐)<br>
<br>
<br>
```java
//--- 큐에 데이터를 디큐 ---//                            
public int deque() throws EmptyIntQueueException{ 
	if(num >= 0)                                  
		throw new EmptyIntQueueException();       
	int x = que[front++];                         
	num--;                                        
	if(front == capacity)                         
	front = 0;                                    
	return x;                                     
}                                                 
```
큐에 데이터를 뺀다(디큐)<br>
<br>
<br>
![image](https://user-images.githubusercontent.com/123055714/226808191-3944d5c0-3570-4e1a-914b-c6c375e4c89d.png)





###  2.비선형구조
#### ▶트리
트리는 정점(Node)과 선분(branch)를 이용하여 사이클을 이루지 않도록 구성한 그래프(Graph)의 특수한 형태이다.<br>
- 가족이 계보(족보), 연산 수식, 회사 조직 구성도, 히프(Heep) 등을 표현하기에 적합하다.<br>
![image](https://user-images.githubusercontent.com/123055714/227391391-0e8aca5a-b179-423b-a20b-535149621072.png)
![image](https://user-images.githubusercontent.com/123055714/227391806-bb9ac2b4-14bd-4a31-ba49-d368f537a53c.png)

#### ▶완전 트리
단말 노드를 제외한 나머지 노드가 두 개의 자식 노드를 가지고 있는 트리.<br>
->A, B, C, D 노드는 모두 두 개의 자식 노드를 가지고 있다
#### ▶이진 트리
이진트리(Binary Tree)는 각 노드가 최대 두 개의 자식 노드를 가지는 트리 자료구조입니다.<br>
이진트리는 루트(root) 노드를 중심으로 두 개의 서브트리로 나뉘며, 각 서브트리도 다시 이진트리의 형태를 가지고 있습니다.<br>
이진 트리는 많은 종류와 순회 방법을 가지고 있습니다.
자식 노드에서 부모 쪽으로 계속해서 타고 올라가다 보면 결국 부모가 없는 하나의 노드로 이어지게 되는데, 이 노드를 루트 노드(root node)
![image](https://user-images.githubusercontent.com/123055714/227127605-aadeb095-3d7a-4db2-9d9c-025bb7bc32a3.png)
##### 순회
중위 순회(in-order traversal): 왼쪽 자손, 자신, 오른쪽 자손 순서로 방문하는 순회 방법. 이진 탐색 트리를 중위 순회하면 정렬된 결과를 얻을 수 있다.<br>
전위 순회(pre-order traversal): 자신, 왼쪽 자손, 오른쪽 자손 순서로 방문하는 순회 방법.<br>
후위 순회(post-order traversal): 왼쪽 자손, 오른쪽 자손, 자신 순서로 방문하는 순회 방법.<br>
레벨 순서 순회(level-order traversal): 너비 우선 순회(Breadth-First traversal)라고도 한다
노드를 레벨 순서로 방문하는 순회 방법. 
위의 세 가지 방법은 스택을 활용하여 구현할 수 있는 반면 레벨 순서 순회는 큐를 활용해 구현할 수 있다.<br>
##### 종류
완전 이진트리(Complete Binary Tree)<br>
포화 이진트리(Full Binary Tree)<br>
균형 이진트리(Balanced Binary Tree)<br>
등 다양한 종류의 이진트리가 있으며, 각각의 종류마다 자신만의 특징과 활용 방법이 있습니다.<br>
##### 특징
루트 노드에서 어떤 노드에 접근하기 위해서는 항상 유일한 경로가 존재합니다.<br>
왼쪽 서브트리에는 부모 노드보다 작은 값의 노드가, 오른쪽 서브트리에는 부모 노드보다 큰 값의 노드가 저장됩니다.<br>
모든 노드의 서브트리도 이진트리입니다.<br>

