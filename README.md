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
FILO<br>
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
FIFO<br>
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
