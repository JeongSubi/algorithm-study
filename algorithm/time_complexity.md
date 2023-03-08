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
```
// BST(Binary Search Tree)
: 원하는 값을 탐색할 때, 노드를 이동할 때마다 경우의 수가 절반으로 줄어든다.

이해하기 쉬운 게임으로 비유해 보자면 up & down을 예로 들 수 있다.
1~100 중 하나의 숫자를 플레이어1이 고른다. (30을 골랐다고 가정한다.)
50(가운데) 숫자를 제시하면 50보다 작으므로 down을 외친다.
1~50중의 하나의 숫자이므로 또다시 경우의 수를 절반으로 줄이기 위해 25를 제시한다.
25보다 크므로 up을 외친다.
경우의 수를 계속 절반으로 줄여나가며 정답을 찾는다.

매번 숫자를 제시할 때마다 경우의 수가 절반이 줄어들기 때문에 최악의 경우에도 7번이면 원하는 숫자를 찾아낼 수 있게 된다.
```

<br/>

### O(n^2)
시간복잡도 O(n^2)은 quadratic complexity라고 부르며,
입력값이 증가함에 따라 시간이 n의 제곱수의 비율로 증가하는 것을 말한다.

즉 입력값의 크기가 1에서 5로 증가하면 5의 제곱인 25초가 증가하는 것이다.

<img width="300" alt="스크린샷 2023-03-08 오후 12 54 25" src="https://user-images.githubusercontent.com/86769182/223615913-c6764bf0-8df9-465c-b43e-cebd9813b9ea.png">

> O(n^2)의 예시

O(n2) 의 대표적인 알고리즘 으로는 버블 정렬(Bubble Sort) 가 있다.

```
function O_quadratic_algorithm(n) {
  for (let i = 0; i < n; i++) {
    for (let j = 0; j < n; j++) {
      // do something for 1 second
    }
  }
}
function another_O_quadratic_algorithm(n) {
  for (let i = 0; i < n; i++) {
    for (let j = 0; j < n; j++) {
      for (let k = 0; k < n; k++) {
        // do something for 1 second
      }
    }
  }
}
```

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
