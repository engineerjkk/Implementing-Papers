# Deep Residual Learning for Image Recognition CVPR 2016
- 깊은 네트워크를 학습시키기 위한 방법으로 잔여 학습(residual learning)을 제안한다.
- layer가 너무깊으면 오히려 에러가 높았다. -> 오히려 더 성능이 안좋았다.
- 일반적인 CNN에서는 단순히 어느 시점부터는 성능이 더 떨어졌다.

- 일반적으로 CNN에서 레이어가 깊어질수록 채널의 수가 많아지고 너비와 높이는 줄어듭니다.
- 컨볼루션 레이터의 서로 다른 필터들은 각각 적절한 특징 feature 값을 추출하도록 학습됩니다.
![image](https://user-images.githubusercontent.com/76835313/142805086-67b464d8-5919-4613-b9bb-116942254ae7.png)

2015년도 VGG와 GoogleNet이 각 7.3, 6.7 error율과 19 Layer과 22Layer로 승부를 보고있을 당시 152Layer 까지 끌어올리면서 에러율 3.57%로 우승을 하였다. 

1. 처음 제안되었던 Skip Connection 구조로, Feature를 추출하기 전 후를 더하는 특지이 있다.
2. 일반 구조(왼쪽)에서 표현 가능한 것은 Residual 구조(오른쪽)에서도 표현이 가능하다. -> **feature를 뽑아서 이전 feature와 더한다.**


![image](https://user-images.githubusercontent.com/76835313/142958645-ecc0b094-33f6-492c-912f-5006ce927c0e.png)
1. Conv1 거친 후
- ![image](https://user-images.githubusercontent.com/76835313/142958703-1cee2676-259d-4740-b86c-fbb7cddb6596.png)
2. Conv2 거친 후
- ![image](https://user-images.githubusercontent.com/76835313/142958735-f3e16a84-feca-4f2d-a71e-98427e9f951c.png)
3. Conv3 거친 후
- ![image](https://user-images.githubusercontent.com/76835313/142958769-89506cff-0bfe-4477-aea1-9c6fdcbe5063.png)
- ![image](https://user-images.githubusercontent.com/76835313/142958817-67cf8517-bec0-446e-8cce-fdb22f262540.png)
4. Conv4 거친 후
- ![image](https://user-images.githubusercontent.com/76835313/142958844-3ffe0044-dbd9-42e6-8ef5-beff6d1af8bb.png)
- ![image](https://user-images.githubusercontent.com/76835313/142958852-5b5c172c-0e7b-4c2b-aea2-f5e966425ab1.png)
5. Conv5 거친 후
- ![image](https://user-images.githubusercontent.com/76835313/142958866-36d2a194-8c8f-45d5-8536-74e9db75f51f.png)
- ![image](https://user-images.githubusercontent.com/76835313/142958914-d05c5d29-4fcb-4e48-9ab0-4fe469ed9861.png)
학생


appendix
1. https://viso.ai/deep-learning/resnet-residual-neural-network/
2. https://github.com/meng1994412/ResNet_from_scratch
