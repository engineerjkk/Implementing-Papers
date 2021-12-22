* 원본 논문과 차이점

1. Random Elastic Deformation 을 구현하지 않았습니다.
- 원본데이터 512 by 512를 넣어주었으며 제로패딩=1 을 넣어주어 convolution 연산에서의 feature map 축소를 방지하였습니다.
- 따라서 input size가 512이며 output size 역시 512입니다.
- 그럼에도 불구하고 결과가 잘 나오는 이유는 Batch Normalization 기법을 사용해주었기 때문이라고 생각합니다.
- 2015년도 당시에는 Batch Normalization(2016)이 없었기 때문에 이 기법을 사용하지 않았습니다.
- 따라서 개인적인 생각으로는 당시의 Data Augmenation인 Random Elastic Deformation을 통해 성능을 높인것과
- 현재 제가 Random Elastic Deformation을 사용하지 않고 Batch Normalization을 사용한것이 서로를 상쇄시켜 비슷한 테스트 에러율을 가진거라고 봅니다.


![image](https://user-images.githubusercontent.com/76835313/146767685-754df186-cd96-4b98-a889-f03a9bb2e4d5.png)
![image](https://user-images.githubusercontent.com/76835313/146767747-fc009fe1-c5a3-4a04-a678-ce5650b84381.png)
![image](https://user-images.githubusercontent.com/76835313/146767798-e175e898-5dd9-4c53-84fa-c45eed1e91a2.png)
![image](https://user-images.githubusercontent.com/76835313/146767827-e06b20e0-5cac-44b9-b5ee-493daf4d4cd1.png)
