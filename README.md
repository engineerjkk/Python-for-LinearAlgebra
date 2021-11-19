# Python-for-LinearAlgebra

![image](https://user-images.githubusercontent.com/76835313/142559925-a2803149-63f1-47d1-9593-13ba3fda6bb6.png)

- ![image](https://user-images.githubusercontent.com/76835313/142559972-1ba60017-8a2d-4bf5-8c03-fc4f4db19490.png)
- 현재 transpose되므로 3 by 1 matrix를 갖는다. 이것이 아래와 덧셈 연산으로 진행되게 된다.
- ![image](https://user-images.githubusercontent.com/76835313/142560029-2630a60c-31dd-49c3-9571-f782caeed90a.png)
- 그렇게되면 p1,p2,p3는 vector matrix이므로 3 by 3 이며, a1~은 3 by 1이다. 이 둘을 연산하게되면 3 by1이 된다. 

- 따라서 둘의 덧셈 연산을 하게되면 IR~ 부분의 1행 부분이  모든 매트릭스에 덧셈, 즉 골고루 분포 따라서 2행, 3행도 마찬가지고 골고루 분포되게된다.
- 그렇기 때문에 aigenvalue가 오름차순이든 내림차순이든 R G B 어느 한쪽에 focus되는 현상은 없으니 걱정할 필요는 없다. 골고루 분포된다.

- ![PCAexample](https://user-images.githubusercontent.com/76835313/142560315-67add0ca-29b7-44ad-917e-a22f61856677.gif)
* 고차원 데이터
1. 변수의 수가 많음 -> 불필요한 변수 존재
2. 시각적으로 표현하기 어려움
3. 계산 복잡도 증가 -> 모델링 비효율적
4. 중요한 변수만을 선택 -> 차원축소

* 변수 선택 (selection) : 분석 목적에 부합하는 소수의 예측 변수만을 선택
- ex) x1~x100이 잇다면 중요한 변수 x1, x5, x25를 뽑는다.
- 장점 : 선택한 변수 해석 용이
- 단점 : 변수간 상관관계 고려 어려움 

* 변수 추출 (extractioin) : 예측변수의 변환을 통해 새로운 변수 추출
- ex) z=f(x1,...,x100)
- 장점 : 변수간 상관관계 고려, 일반적으로 변수의 개수를 많이 줄일 수 있음
- 단점 : 추출된 변수의 해석이 어렵다.(z 처럼 원래 변수의 결합으로 이루어져있기 때문이다.)
- ![image](https://user-images.githubusercontent.com/76835313/142571002-2fc5a921-a494-43fd-b6b5-02f444a3f4ec.png)
1. 변수선택 : feature selection
2. 변수 추출 : feature extraction

1. Supervised feature selection : y를 이용해서 한다.
2. Supervised feature extraction : y를 이용하는데 x의 결합
3. Unsupervised feature selection : PCA loading -> 비지도 변수 선택법이다. x의 상관관계만으로 중요한 x를 추출 
4. Unsupervised feature extraction  : Principal Components Analysis 비지도 변수추출방법 y를 이용하지않고 x값을 추출한다.

* 주의할점
1. **Principal(가장중요한, 교장선생님) Components Analysis**
2. **Principle(원리) Components Analysis**

* PCA 개요
1. 고차원 데이터를 효과적으로 분석하기 위한 대표적 분석 기법
2. 차원축소, 시각화, 군집화, 압축 -> 차원축소를 함으로써 시각화, 군집화, 압축을 할 수 있게 된다.

- PCA는 n개의 관측치와 p개의 변수로 구성된 데이터를 상관관계가 없는 k개의 변수로 구성된 데이터 (n개의 관측치)로 요약하는 방식으로, 이 때 요약된 변수는 **기존 변수의 선형조**으로 생성된다.
- **원래 데이터의 분산을 최대한 보존**하는 새로운 축을 찾고, 그 축에 데이터를 사영(Projection) 시키는 기법

* 주요 목적
1. 데이터 차원 축소 (n by p -> n by k, where k << p) : 현저히 작은.
2. 데이터 시각화 및 해석
3. 일반적으로 PCA는 전체 분석 과정 중 초기에 사용된다.
- 모델링 전에 데이터가 어떻게 생겼나 보고싶을 때
- 데이터 변수가 너무많아 효율적으로 줄일때

1. 관측치 N, 변수가 P일때 관측치는 그대로두고 변수를 줄인다. 

- ![image](https://user-images.githubusercontent.com/76835313/142572483-d9f8221e-b1d1-46b0-b033-0f965adeba72.png)
원래 데이터의 차원을 줄였음에도 잘 보존하는 것을 볼 수 있다.

* **Z is a linear combination (선형결합) of the original all p variables in X -> 모든 x변수를 가지고 선형결합을 한다. 
- Z1, Z2,...,Zp : 각 기저로 사영변환 후 변수로 **주성분** 변수가 된다. score라고 부른다. 
- 분산을 최대화, 최소화 시키는 축은 어느것일까?
- ![image](https://user-images.githubusercontent.com/76835313/142573648-a30de5af-1653-47b0-91c8-da30e540cd64.png)
- 그 축에 사영시키면 그림자라는 뜻인데 아래와 같이 바뀌게 된다. -> PCA가 찾고자하는 축이된다.
- ![image](https://user-images.githubusercontent.com/76835313/142573740-33eadb20-3de3-4d01-911e-9086b8d0b849.png)
- 최소화된 것은 아래와 같다.
-  ![image](https://user-images.githubusercontent.com/76835313/142573829-0676f84c-b25a-4983-b3cd-1df278f56633.png)

따라서 1번의 분산이 더 크다.  

* 고유값 및 고유벡터(ㅎ+한자)
- 어떤 행렬 A에 대해 상수 λ와 벡터 x가 다음 식을 만족할 때, λ와 x를 각각 행렬 A의 고유값(eigenvalue) 및 고유벡터(eigenVector)라고 한다.
1. 만약 P by P 행렬이 있다면 이 행렬의 고유값이 P개의 고유값 eigenvalue가 나타난다. 
2. 그리고 각 eigenvalue마다 벡터가 구해지는데 이때 eigenVector가 구해진다.
3. 따라서 P by P 행렬이 주어졌을때 P개의 Value와 P개의 Vector가 구해지는 것이다. 

![image](https://user-images.githubusercontent.com/76835313/142574804-df1a311c-0e2b-487d-8d30-2c3a1d3b23b6.png)
1. A는 주어진 행렬
2. X가 eigen vector
3. λ는 eigenValue이다. 

* 따라서 벡터에 행렬을 곱한다는 것은 해당 벡터를 선형변환 Linear transformation 한다는 의미이다. -> 고유벡터는 이 변환에 의해 방향이 변하지 않는 벡터를 의미한다.
(eigen은 독일어로 특징을 의미한다. 따라서 행렬의 특징값정도로 받아들이면 될 듯 하다. 그래서 행렬의 고유한 특징적인 값과 벡터라 볼 수 있다.)

- ![image](https://user-images.githubusercontent.com/76835313/142575214-c7bd1efa-94c8-4510-951a-fb11a87c3763.png)
- Z는 우리가 구하고싶은 새로운 변수이다.
- 원래변수의 선형결합으로 구성되어있다. X는 원래 주어진 데이터이므로 알파만 구하면 된다.
-> Z의 분산을 최대화하는 알파를 찾는다.  
 
