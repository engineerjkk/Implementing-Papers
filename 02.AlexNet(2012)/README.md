![image](https://user-images.githubusercontent.com/76835313/141393376-cfdf2031-ab34-494c-b758-41396b1ec7bd.png)

* AlexNet 이전
- 기존 Object Recognition에서 머신러닝 기법이 일반화 되어 있었다.
- 대표적인 예로 SVM
- 머신러닝 사용시 small dataset은 좋은 성능을 냈으나, 성능이 좋은 일반화를 위해 Larger dataser을 학습시켜야 한다.

* AlexNet
- 머신러닝 기법의 탈피 : 심층 신경망 모델 사용
- 심층 신경망 모델 : Vanishing Gradient 문제 해서
- Larger Dataset 사용
- GPU를 사용 (GTX580)
- 과대적합 방지 : Dropout

- Vanishing Gradient 문제를 해소하기 위하여 ReLU Activation Function 사용
1. 학습 속도가 빠르다(Gradient가 0또는 1): 학습속도 6배 이상 개선
2. Non-Saturation 활성함수 : 값이 크면 클수록 더 큰 Gradient
3. Vanishing Gradient 문제 해소(완벽히는 X)

1. 1 Layer
- 3은 RGB를 의미한다.
- 11 by 11 filter를 아래 위로 48개와 96개를 사용했다.
![image](https://user-images.githubusercontent.com/76835313/141452037-b4d231a6-1a1c-4a3b-abdb-cdc786820845.png)

1. Convolution 1에서는 Edge+Blob을 추출한다.
2. Convolution 3에서는 Texture를 추출한다.
3. Convolution 5에서는 Object arts를 추출한다.
4. Convolution 8에서는 Object Classes를 추출한다.

# Sequence
1. the input image is of size 224 x 224 x 3, where the 3 represents the RGB channel of a color image

2. 96 Kernels of size 11 x 11 x 3 with a stride of 4 pixels

# Overall Architecture
1. Input Layer of Image Size (224 x 224 x 3)  

2. Convolutional Layer (96 x (11 x 11 x 3)) + stride size of 4  

Bias with constant value of 1  
ReLU Activation  
Local Response Normalization  
Max Pooling (Overlapping Pooling)  
3. Convolutional Layer (256 x (5 x 5 x 48))  

ReLU Activation  
Local Response Noramlization  
Max Pooling (Overlapping Pooling)  
4. Convolutional Layer (384 x (3 x 3 x 128))  

Bias with constant value of 1  
5. Convolutional Layer (384 x (3 x 3 x 192))  

Bias with constant value of 1  
6. Convolutional Layer (256 x (3 x 3 x 192))  

Max Pooling (Overlapping Pooling)  
7. Fully Connected Layer (4096)  

Bias with constant value of 1  
Dropout  
8. Fully Connected Layer (4096)  

Bias with constant value of 1  
Dropout  
9. Fully Connected Layer (1000)  


![image](https://user-images.githubusercontent.com/76835313/141453903-7ca8d8ab-7dcb-4881-b3e7-d5656001a3b3.png)
![image](https://user-images.githubusercontent.com/76835313/141453926-6ed8e7a7-cd71-4392-8386-11f23d84ec89.png)

# Link
1. https://medium.com/@smallfishbigsea/a-walk-through-of-alexnet-6cbd137a5637
2. https://www.mydatahack.com/building-alexnet-with-keras/
3. https://medium.com/geekculture/a-2021-guide-to-improving-cnns-network-architectures-historical-network-architectures-d23f32afb1bd
4. https://github.com/toxtli/alexnet-cifar-10-keras-jupyter/blob/master/alexnet_test4.ipynb
5. https://kratzert.github.io/2017/06/15/example-of-tensorflows-new-input-pipeline.htmlb
6. https://colab.research.google.com/drive/1LftAExC3XGgcHkhIHQQ6aGWrlxkZv-1x?usp=sharing#scrollTo=abtguzXDbom7
      In the end, the network’s size is limited mainly by the amount of memory available on current GPUs and by the amount of training time that we are willing to tolerate. 
      Our network takes between five and six days to train on two GTX 580 3GB GPUs. 
      All of our experiments suggest that our results can be improved simply by waiting for faster GPUs and bigger datasets to become available.


      결국, 네트워크의 크기는 주로 현재 GPU에서 사용할 수 있는 메모리의 양과 우리가 허용하고자 하는 훈련 시간의 양에 의해 제한된다.
      우리의 네트워크는 두 개의 GTX 580 3GB GPU로 훈련하는 데 5~6일이 걸린다.
      우리의 모든 실험은 GPU와 더 큰 데이터셋을 사용할 수 있기를 기다리는 것만으로도 결과를 개선할 수 있음을 시사한다.
      
# 대화
JK : AlexNet 구현중인데요. 실제 논문은 첫번째 그림과 같은데 다들 이렇게 2 Level로 하는것을 생략하고 아래와 같이 하더라구요 혹시 논문 정석대로 구현한 설명이나 코드를 보고싶은데 혹시 아시는분 계신가요???  
C : 저거 두개 쪼갠건 vram 딸려서 그런거 아님?
JK : 그렇다고보기엔 모든 구현이 다그렇더라구요 그리고 논문구현은 2012년때 GTX580으로 구현한건데 지금은 더 넉넉하게 가능하지않나요?
A : 요게 사실 지금 같으면 모델 하나를 gpu 두개에 올리면 되는데 당시엔 그렇지를 못했던 것으로 기억해요. 그래서 그냥 모델을 두개로 쪼개서 각각 다른 gpu에 옿렸던 것으로 기억하는데 자세한 건 논문으로....
JK : 위에 분이 말씀하신 vram 딸려서라는 말도 관계가 있나요? 
A : 저도 정확히 기억나는 내용은 아니라 조십스러운데 동일한 맥락일겁니다. 저게 사실 걍 채널 수 2배 한거랑 차이점이 많지 않자나여.
B : vram이 부족해서 model parallelism을 도입한 게 맞습니다. 하지만 2 x #channels와 동치는 되지 않구요.
A : 네 완전 동치는 아니져
B : alexnet 논문에서 언급하듯 각  gpu에서 서로다른 feature를 학습했구요(형태 /색상), 단순히 channel만 합친 대다수의 구현에서는 논문에 report된 성능을 재현하지 못했습니다.
5~6년 전쯤에 theano로 구조만 동일하게(model parallelism없이 구현해서 gpu에서 레이어만 병렬로 분리) 실험했었는데 그때도 논문 성능 재현은 안되었구요.
논문처럼 형태/색상 filter가 나눠지지도 않아서 굉장한 우연의 산물로 생각했던 적이 있습니다.
JK : 그런데 feature만 따로 학습은 하지만 다시 classifier부분에서 만나는데 하나의 GPU로는 안되나보죠?
B : gpu나눠서 구현해보시면 그것도 흥미로운 결과가 될 것 같네요. 하나의 gpu로도 구현 가능합니다.
JK : 그리고 feature extractor 부분에서도 cross 되는부분이 있어서요.
JK : 아 당시 GPU메모리가 딸려서 하나의 GPU로 못하니 두개의 GPU를 써서 두 네트워크를 크로스한건가봅니다. 그럼 현재 실제 구현을 할때 굳이 저 논문 그림대로 할 필요는 없네요??
B : 네 저 그림대로 할 필요 없구요 구조를 동일하게 가져가고싶으시면 레이어를 병렬배치하시면 됩니다.
JK : 감사합니다 ㅎ

- kernels in layer 4 take input only from those kernel maps in layer 3 which reside on the same GPU.
- Layer 4의 커널은 동일한 GPU에 존재하는 계층 3의 커널 맵에서만 입력을 받습니다.

- Choosing the pattern of connectivity is a problem for cross-validation, but this allows us to precisely tune the amount of communication until it is an acceptable fraction of the amount of computation.
- 연결 패턴을 선택하는 것은 교차 검증의 문제이지만, 이것은 우리가 그것이 계산량의 허용 가능한 부분이 될 때까지 통신량을 정밀하게 조정할 수 있게 해준다.

![image](https://user-images.githubusercontent.com/76835313/141471670-cb1b581e-666d-49f6-bab1-f2b91f4394e8.png)

### 즉, Multi GPUs 로 넘어가기 때문에 이번 연구 범주를 넘게됩니다. 따라서 현 시점에서는 하나의 GPU로도 가능하기때문에 2 Level로 나누지 않고 하나의 Level로도 충분히 AlexNet 구현이 가능하기 때문에 이부분이 실제 논문과 차이가 있는점 미리 말씀드립ㄴ디ㅏ.
