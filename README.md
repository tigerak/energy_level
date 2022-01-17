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

3차원 분자 구조 정보를 이용하여 Random Forest와 Boost 모델로 간단한 베이스라인을 만들고

그래프 신경망을 이용하여 성능을 높이고자 합니다.

## Test Result

3차원 구조 정보 사용

- **Random Forest** - [MSE] public점수 : 0.273 // private점수 : 0.249
- **XGBoost** - [MSE] public점수 : 0.278// private점수 : 0.249

SMILES 화학식만 이용

- **GCN (Graph Convolutional Networks) -** [MSE] public점수 : 0.449 / private점수 : 0.380
- **RGCN (Relational GCN)** -  [MSE] public점수 : 0.123 / private점수 : 0.130
