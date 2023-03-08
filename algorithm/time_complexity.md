# 시간 복잡도(Time Complexity)

### 시간 복잡도(Time Complexity)란?

어떠한 연산을 실행할 때 연산 횟수에 비해 시간이 얼마나 걸리는지 나타내는 것이다.
효율적인 방법으로 문제해결을 할 때 시간복잡도도 항상 고려대상에 포함되어야 한다.

시간복잡도는 Big-O(빅-오), Big-Ω(빅-오메가), Big-θ(빅-세타) 표기법이 있는데,
Big-O는 최악, Big-Ω는 최선, Big-θ는 평균에 대해 나타내는 표기법이다.

문제해결시 최악에 대해 고민하는것이 중요하므로 Big-O 표기법을 많이 사용한다.

<br/>

## Big-O 표기법의 종류

### O(1)

시간복잡도 O(1) 은 constant complexity 라고도 하며, 입력값이 증가하더라도 시간이 늘어나지 않는다.

즉 입력값의 크기가 증가해도 바로 출력값을 얻을 수 있다.


<img width="300" alt="스크린샷 2023-03-08 오후 12 53 46" src="https://user-images.githubusercontent.com/86769182/223615668-f40e69f1-c1ba-4629-b6ed-fed7b4f445e1.png">

> O(1) 의 예시

```
//arr의 크기가 아무리 커도 시간복잡도가 증가하지 않는다.
function funcOne(arr){
  return arr[1];
}
```

<br/>

### O(n)
시간복잡도 O(n)은 linear complexity 라고도 하며 입력값 증가에 따라 같은비율로 증가한다.

예를들면 입력값이 1이면 1초가 걸리는 문제라면, 100이라면 100초가 된다.

<img width="300" alt="스크린샷 2023-03-08 오후 12 53 55" src="https://user-images.githubusercontent.com/86769182/223615870-bf769964-39cd-4a18-b842-f880e147665c.png">

> O(n)의 예시

```
//arr의 길이만큼 반복(즉 arr가 증가하면 시간도 같은비율로 증가)
function funcTwo(arr){
  let max = 0;
  for(let i=0; i<arr.length; i++){
    if(arr[i] > max)
      max = arr[i];
  }
  return max;
}
```

<br/>

### O(log n)
시간복잡도 O(log n)은 logarithmic complexity 라고도 하며, 입력값이 증가할수록 시간 증가율이 하락한다.

<img width="300" alt="스크린샷 2023-03-08 오후 12 57 54" src="https://user-images.githubusercontent.com/86769182/223616066-e133a8ff-2ccb-4f08-a7dd-07e2d5cd48b2.png">

> O(log n)의 예시

O(log n)의 대표적인 알고리즘 으로는 병합 정렬(Merge Sort) 가 있다.

<br/>

### O(n^2)
시간복잡도 O(n^2)은 quadratic complexity라고 부르며,
입력값이 증가함에 따라 시간이 n의 제곱수의 비율로 증가하는 것을 말한다.

즉 입력값의 크기가 1에서 5로 증가하면 5의 제곱인 25초가 증가하는 것이다.

<img width="300" alt="스크린샷 2023-03-08 오후 12 54 25" src="https://user-images.githubusercontent.com/86769182/223615913-c6764bf0-8df9-465c-b43e-cebd9813b9ea.png">

> O(n^2)의 예시

O(n2) 의 대표적인 알고리즘 으로는 버블 정렬(Bubble Sort) 가 있다.

<br/>

### O(2^n)
시간복잡도 O(2^n)은 exponential complexity 라고도 하며, 가장 느린 시간복잡도를 가진다.
O(2^n)으로 구현한 알고리즘은 매우 느리므로 O(2^n) 으로 구현된 알고리즘 이라면 다시 구현할 필요가 있다.

<img width="300" alt="스크린샷 2023-03-08 오후 2 21 52" src="https://user-images.githubusercontent.com/86769182/223626438-8527ebea-abe5-414b-bfd1-0d8a7e741080.png">


> O(2^n) 의 예시 

O(2^n)의 대표적인 알고리즘 으로는 재귀적으로 구현된 피보나치(fibonacci) 수열이 있다.

```
function fibonacci(n){
  if(n <= 1){
    return 1;
  }
  return fibonacci(n-1) + fibonacci(n-2);
}
```
