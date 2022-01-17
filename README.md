# 3차원 분자 구조를 활용한 Ennrgy Gap 예측

[DACON Competition](https://dacon.io/competitions/official/235789/overview/description)

## 개요

1. **프로젝트 배경**
    
    최근 머신러닝을 이용하여 화학 분자구조로부터 물성을 예측하는 연구가 활발히 이루어지고 있습니다.
    화학 구조는 각 분자를 구성하는 원자들과 그 원자들과의 연결을 형성하는 결합의 종류에 따라서 방대한 영역의 정보를 담아낼 수 있으며, 이 정보를 효과적으로 활용할 수 있는 AI 모델링 기법이 예측 성능에 큰 영향을 미칩니다.
    이러한 예측 모델을 통하여 반도체, 디스플레이 분야 신소재 개발 및 신약 등 다양한 분야에서 핵심적인 역할을 할 수 있습니다
    
2. **목적**
    
    분자의 3차원 구조 정보를 이용하여 S1-T1 사이의 에너지 갭을 추정할 수 있는 머신 러닝 알고리즘을 개발하는데 목적이 있습니다.

## 계획

3차원 분자 구조 정보를 이용하여 Random Forest와 Boost ****모델로 간단한 베이스라인을 만들고

그래프 신경망을 이용하여 성능을 높이고자 합니다.

1. **Boosting**
    
    ![img1.daumcdn.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/817f4f37-6c06-452e-8f6c-03760eb22b9c/img1.daumcdn.png)
    
    bagging의 경우 각각의 분류기들이 학습시 상호 영향을 주지 않은 상황에서(독립적) 학습이 끝난 다음 결과를 종합하는 기법이라면, boosting은 이전 분류기의 학습 결과를 토대로 다음 분류기의 학습 데이터의 샘플 가중치를 조정해 학습을 진행하는 방법입니다.
    즉, 먼저 생성된 모델을 꾸준히 개선해 나가는 방향으로 학습이 진행되는 것입니다.
    이러한 부스팅기법은 일반적으로 오답에 대해 높은 가중치를 부여하므로 정확도가 높게 나타납니다. 하지만 그렇기 때문에 outlier에 취약할 수 있습니다.
    
2. **GCN - 그래프 합성곱 신경망이란?**
    
    ![0_z5jz2rW8gQ2UaqsV.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8ae9577e-2811-4fd9-87ea-19100090f948/0_z5jz2rW8gQ2UaqsV.png)
    
    ![노드와엣지합성곱.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e921c7c5-8b9a-404a-bc67-6159633bccbc/노드와엣지합성곱.png)
    
    합성곱 연산이 한번 일어나면 한 번 까지의 관계를, 두 번 일어나면 두 번 까지의 관계 정보를 계산할 수 있습니다.
