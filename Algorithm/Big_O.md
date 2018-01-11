# Big O
### ※Big-O definition : __measures time & space complexity__ ####

- Big O = asymptotic runtime (점근적 실행 시간). 

  - Big-O : __maximum runtime__. Assumes that in the long term, the time needed to run the function approaches Big-O time.
  - Big-Omega : __minimum runtime__. Opposite of Big-O. No process can take less time than Big-Omega.
  - Big-Theta : In IT field, __equals to Big-O.__

- Best-case, Worst-case, average-case scenarios

   best-case scenario doesn't mean that much. 
   Keep in mind that worst-case & average-case scenarios are the ones that count.

- There's tradeoff between time complexity and space complexity. -> Inverse relationship!


> #### When calculating complexity, constants must be ignored! ####

> #### So do non-prime terms! (i.e. O(x^2 + 3x) -> O(X^2)) ####

-------------------------------

### multi-part algorithm : addition VS multiplication

* Addition -> O (A+B) 

  ```java
  for(a in arrA) {
      print(a);
  }
  
  for(b in arrB) {
      print(b);
  }
  ```

* Multiplication -> O(A*B)

   ```java
   for(a in arrA){
       for(b in arrB){
           print(a + ":" + b)
       }
   }
   ```

> ArrayList - 배열로 만들어짐. 배열의 용량이 꽉차려고 할 때 ArrayList 클래스는 기존보다 크기가 2배인 배열을 만든 후에 기존 배열의 원소를 전부 복사시킴.



* #### complexity - Log N ####
  
   Log N은 계속 반으로 작아질 때. Log 가 2의 exponential의 반대이기 때문에.
   즉, 호출될 때마다 Big-O가 반으로 줄어든다면, 그 로직의 complexity는 Log N이 된다.

   Log N의 하위 항은 상수항으로 취급되기 때문에, Big-O notation에서 로그의 하위항은 무시해도 좋다. 하지만 exponent의 경우는 이야기가 달라진다. 
   지수의 밑은 무시하면 안된다. 
