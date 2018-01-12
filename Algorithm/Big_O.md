<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>

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
   
 ### 중요! 
  알고리즘의 Big-O를 계산할 때는, 대상 데이터 (Object, array, etc)가 동일 데이터를 대상으로 하는지, 다른 데이터를 대상으로 하는지를 꼭 확인하도록 한다. 

```java
// arrayA 와 arrayB 배열은 다른 데이터이기 때문에, 알고리즘 계산할 떄, O(^2)로 되면 안됨!
void printUnorderedPairs(int[] arrayA, int[] arrayB){
    for(int i = 0 ; i < arrayA.Length ; i++){
        for(int j =0 ; j < arrayB.Length ; j++) {
            System.Println(arrayA[i] + arrayB[j]);
        }
    }
}
````

 ### 중요! 
  알고리즘의 Big-O를 계산할 때는, 대상 데이터 (Object, array, etc)가 동일 데이터를 대상으로 하는지, 다른 데이터를 대상으로 하는지를 꼭 확인하도록 한다. 

```java
// arrayA 와 arrayB 배열은 다른 데이터이기 때문에, 알고리즘 계산할 떄, O(^2)로 되면 안됨!
// 올바른 방법은 arrayA 따로, arrayB 따로 해야함.
// 때문에 Big-O는 O(ab)로 되어야 함.
void printUnorderedPairs(int[] arrayA, int[] arrayB){
    for(int i = 0 ; i < arrayA.Length ; i++){
        for(int j =0 ; j < arrayB.Length ; j++) {
            System.Println(arrayA[i] + arrayB[j]);
        }
    }
}
```

* 예제 8번 (p.75) 여러 개의 string이 unordered된 List가 주어졌을 때, 각각의 문자열을 먼저 정렬하고, 그 다음에 전체 문자열을 abc 순으로 정렬하는 알고리즘이 있을 때, 수행시간은 어떻게 되는가?

  여기서 sort algorithm의 대상 데이터는 String 하나, List 하나이다. 먼저 String을 정렬하고, 그 후에 리스트를 정렬하기 때문에.
  각 부분의 time complexity는 다음과 같다.

  1. 제일 긴 String을 정렬하는 알고리즘 -> O(n Log n) // 정렬이면 O(n Log n)인가?
  2. String이 a개 있다고 한다면, O(a * n Log n) 이다.
  3. 전체 List를 __탐색__ 그리고 __정렬__ 하는 시간이 필요함. 총 a개의 string이 있기 때문에, 탐색하는 시간을 O(a), 정렬하는 시간을 O(m Log m)이라고 한다면, 답은 O(a * m Log m)이다.
  4. 위의 두 부분을 더해주면 O(a* (m Log m + n Log n))이 된다.


### 중요!
  __재귀 알고리즘을 볼 때는, 하나의 메소드 안에서 분기가 몇개가 되는가에 따라서 exponentially 증가한다.__
  
  __예를 들어 하나의 메소드에서 자기 자신을 총 2번 부른다면 O(2^n)이 된다.__

    
