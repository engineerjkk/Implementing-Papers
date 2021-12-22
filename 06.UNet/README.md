* 추가내용

1. 원본 논문과 차이점
- Random Elastic Deformation 을 구현하지 않았습니다.
- 원본데이터 512 by 512를 넣어주었으며 제로패딩=1 을 넣어주어 convolution 연산에서의 feature map 축소를 방지하였습니다.
- 따라서 input size가 512이며 output size 역시 512입니다.
- 그럼에도 불구하고 결과가 잘 나오는 이유는 Batch Normalization 기법을 사용해주었기 때문이라고 생각합니다.
- 2015년도 당시에는 Batch Normalization(2016)이 없었기 때문에 이 기법을 사용하지 않았습니다.
- 따라서 개인적인 생각으로는 당시의 Data Augmenation인 Random Elastic Deformation을 통해 성능을 높인것과
- 현재 제가 Random Elastic Deformation을 사용하지 않고 Batch Normalization을 사용한것이 서로를 상쇄시켜 비슷한 테스트 에러율을 가진거라고 봅니다.

2. d1(x)+d2(x) 이렇게 두개의 식을 쓰는 이유
![image](https://user-images.githubusercontent.com/76835313/147087724-e9cdebd2-191a-4c83-a7d9-6247f05ce272.png)
- 여기서 weight값을 결정하는것이 exp 괄호안의 값입니다. d1+d2값이 클수록 exp 값은 작아집니다. 따라서 세포 경계의 거리와 멀수록 weight값이 작아지는 것입니다.
- 이러한 점에서 d1, d2 두개인 이유는 다음과 같습니다.
- 만약 d1 한개라면 세포밖의 위치해 있어도 그 값이 클것입니다. 하지만 d2가 존재하므로 두번째로 가까운 경계와의 거리가 매우 멀기때문이 d1+d2값은 매우커져 weight 값이 작아질 겁니다.
- 그렇기때문에 이 식의 목적은 각 픽셀이 세포안의 있는가를 결정하기때문에 세포안의 픽셀이 존재할 수록, 가장자리와 가까울수록 weight값은 커집니다. 

![image](https://user-images.githubusercontent.com/76835313/146767685-754df186-cd96-4b98-a889-f03a9bb2e4d5.png)
![image](https://user-images.githubusercontent.com/76835313/146767747-fc009fe1-c5a3-4a04-a678-ce5650b84381.png)
![image](https://user-images.githubusercontent.com/76835313/146767798-e175e898-5dd9-4c53-84fa-c45eed1e91a2.png)
![image](https://user-images.githubusercontent.com/76835313/146767827-e06b20e0-5cac-44b9-b5ee-493daf4d4cd1.png)
