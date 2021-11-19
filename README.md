# Python-for-LinearAlgebra

![image](https://user-images.githubusercontent.com/76835313/142559925-a2803149-63f1-47d1-9593-13ba3fda6bb6.png)

- ![image](https://user-images.githubusercontent.com/76835313/142559972-1ba60017-8a2d-4bf5-8c03-fc4f4db19490.png)
- 현재 transpose되므로 3 by 1 matrix를 갖는다. 이것이 아래와 덧셈 연산으로 진행되게 된다.
- ![image](https://user-images.githubusercontent.com/76835313/142560029-2630a60c-31dd-49c3-9571-f782caeed90a.png)
- 그렇게되면 p1,p2,p3는 vector matrix이므로 3 by 3 이며, a1~은 3 by 1이다. 이 둘을 연산하게되면 3 by1이 된다. 

- 따라서 둘의 덧셈 연산을 하게되면 IR~ 부분의 1행 부분이  모든 매트릭스에 덧셈, 즉 골고루 분포 따라서 2행, 3행도 마찬가지고 골고루 분포되게된다.
- 그렇기 때문에 aigenvalue가 오름차순이든 내림차순이든 R G B 어느 한쪽에 focus되는 현상은 없으니 걱정할 필요는 없다. 골고루 분포된다.

- ![PCAexample](https://user-images.githubusercontent.com/76835313/142560315-67add0ca-29b7-44ad-917e-a22f61856677.gif)
