# Deep Residual Learning for Image Recognition CVPR 2016
- 깊은 네트워크를 학습시키기 위한 방법으로 잔여 학습(residual learning)을 제안한다.
- layer가 너무깊으면 오히려 에러가 높았다. -> 오히려 더 성능이 안좋았다.
- 일반적인 CNN에서는 단순히 어느 시점부터는 성능이 더 떨어졌다.

- 일반적으로 CNN에서 레이어가 깊어질수록 채널의 수가 많아지고 너비와 높이는 줄어듭니다.
- 컨볼루션 레이터의 서로 다른 필터들은 각각 적절한 특징 feature 값을 추출하도록 학습됩니다.
