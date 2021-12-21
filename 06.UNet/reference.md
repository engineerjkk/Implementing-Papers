- https://medium.com/@msmapark2/u-net-%EB%85%BC%EB%AC%B8-%EB%A6%AC%EB%B7%B0-u-net-convolutional-networks-for-biomedical-image-segmentation-456d6901b28a
- https://medium.com/@msmapark2/fcn-%EB%85%BC%EB%AC%B8-%EB%A6%AC%EB%B7%B0-fully-convolutional-networks-for-semantic-segmentation-81f016d76204
- https://www.youtube.com/watch?v=sSxdQq9CCx0
- https://juseong-tech.tistory.com/2
- ![image](https://user-images.githubusercontent.com/76835313/146713368-c1cbc4be-1a70-4387-89d1-255bee4054be.png)
- small k는 해당 클래스 k를 의미하며, Large K는 전체 클래스의 수를 의미한다. 
- ak(x)는 픽셀 포지션 x에서 feature 채널 k안의 activation function을 의미한다.
- ![image](https://user-images.githubusercontent.com/76835313/146713459-7558f1ef-2e8a-4427-a84e-389203723f6e.png)
- wc(x)는 x의 위치에해당하는 클래스의 빈도수에 의해 결정되는 식이다. 학습데이터에서 x픽셀이 백그라운드, forground가 많은지 빈도수에 의해 결정된다.

1. 사전 지식
![image](https://user-images.githubusercontent.com/76835313/146715321-7addc292-a275-459f-90ab-63d2c83d10db.png)

- Sementic Segmentation 분야에서는 FCNs가 사용된다. 
- Fully Convolutional Networks for Semantic Segmentation

1. 클래스가 두개다 forground path와 back ground path, 본 논문에서는 배치사이즈를 크게해서 한 이미지에 대한 배시차이즈를 줄여 효율성을 높이고, 모멘텀을 사용해서 업데이트 할 때 이전 데이터의 영향력을 높였다.   
## https://89douner.tistory.com/297
- https://doubleyoo.tistory.com/m/4
- https://mylifemystudy.tistory.com/87
- https://medium.com/@codecompose/cumedvision1-2e45b94e7b79
- https://velog.io/@minkyu4506/%EB%85%BC%EB%AC%B8-%EB%A6%AC%EB%B7%B0-U-Net-%EB%A6%AC%EB%B7%B0
- https://kuklife.tistory.com/119
- https://lmb.informatik.uni-freiburg.de/people/ronneber/u-net/ 발표영상
- https://ichi.pro/ko/gyocha-enteulopi-sonsil-hamsu-267783942726718
- https://www.hellot.net/news/article.html?no=41604 Cross entropy
