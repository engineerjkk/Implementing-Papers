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
