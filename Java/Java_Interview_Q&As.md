 ## 1. fail-safe vs. fail-fast iterators

  * fail-fast : 런타임 중에 (iteration 중에) `collection`이 바뀌었다면 바로 `ConcurrentModificationException`을 던짐.
  thread-safe하지 않은 Collection들, 즉 ArrayList, HashSet, HashMap 등이 fail-fast하다.

  * fail-safe : 런타임 중에 (iteration 중에) `collection`이 바뀌어도 Exception을 던지지 않음. Thread-safe한 Collection들,
   Vector나 ConcurrentHashMap, ConcurrentArrayList등이 해당.


## 2. `ArrayList`, `LinkedList`, `Vector` 중에서 요소를 집어넣고 빼는데 가장 적합한 자료구조는 무엇인가?

    가장 적합한 것은 LinkedList이다. 

    그 이유는 ArrayList, Vector는 요소를 추가할 때 그 뒤에 있는 요소들을 전부 한 칸 씩 옮겨야 하기 때문이다. Vector는 synchronized이지만,
    그만큼 속도가 느리기 때문에, 왠만하면 ArrayList로 OK.
    
    LinkedList 는 양방향 연결 리스트? 이기 때문에, 배열 중간에 요소를 추가해도, 요소 앞과 뒤의 주소만 새로운 요소로 수정하면 된다.

    다만, random access는 ArrayList가 O(1)이고, LinkedList는 O(n)이니까 ArrayList쪽이 더 적합하다.

## 3. 보안에 민감한 데이터는 왜 String이 아니고 char 배열에 집어넣어야 하는가?

    Java에서는 String은 불변(immutable)하다. 그말인즉슨, String이 만들어지면, GC되기 전까지 String pool에서 계속 남아있다는 것이다. 
    즉, String 값을 조작하고 나서도, String은 String pool에 GC되기 전까지 남아있고, 누군가 memory dump에 접근할 수 있다면, 비밀번호 등의
    보안에 민감한 데이터가 유출될 가능성이 있기 때문에, character 배열 쪽이 더 안전하다.

## 4. `ThreadLocal` 클래스는 무엇인가?
   
    ThreadLocal 인스턴스는 각 Thread 별로 독립적인 값을 저장할 수 있다. 

## 5. `volatile` 은 무슨 뜻인가?

    Java에서는 각 thread가 자기 자신만의 stack을 가지고 있고, 접근 가능한 variable의 copy를 만들어서 stack에 저장한다. 
    `volatile`을 붙이면, thread들이 공유할 수 있는 resource가 되어서 다른 thread에서 값을 access하고 변경할 수 있다.
