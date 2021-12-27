Visual Localization 중 Structure from Motion은 기본이다.
먼저 특징점을 추출하기 위해서 SIFT 기법을 통상 많이 사용하며 각 이미지마다의 추출된 특징점들간의
Correnspondence문제를 해결해줘야한다.
그러기 위해서는 Epipolar geometry 기법을 이해해야 한다. 

첫번째 이미지와 그 다음 이미지 간의 correspondence 문제를 해결하는 데 사용되는
Essential Matrix와 Fundamental Matrix에 대해 중점적으로 알아보겠습니다. 

여기서 Essential Matrix와 Fundamental Matix의 차이는
Camera Instrinsic 값의 여부입니다. 있으면 Essential Mtrix, 없으면 Fundamental Matrix입니다.
즉 calibrated camera가 없으면 Fundamental Matrix를 사용합니다. 하지만 이것은 최소 8개의 값이 있어야하죠
Weak Calibration

1. Cross products
![image](https://user-images.githubusercontent.com/76835313/147447783-b9ce5f15-38e6-42c5-aa34-6d8252e33785.png)
![image](https://user-images.githubusercontent.com/76835313/147447809-779c7ddb-5d67-4485-8628-c370f46ddeb2.png)
![image](https://user-images.githubusercontent.com/76835313/147447829-a716d9db-8126-4a0a-a57f-d36225d822e6.png)

2. Essential Matrix
![image](https://user-images.githubusercontent.com/76835313/147449113-5cf444b7-be3c-4698-8dce-cb01852ea754.png)

3. Fundamental
