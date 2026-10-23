# RBM(제한 볼츠만 머신)의 개발자와 벤지오의 기여

## 1. RBM 개발자는 벤지오인가?

아닙니다. **RBM(Restricted Boltzmann Machine)의 발전에 중심적인 역할을 한 연구자는 제프리 힌턴(Geoffrey Hinton)**입니다. 다만 RBM은 여러 연구자의 성과를 바탕으로 발전했으므로 한 사람의 단독 발명으로 단정하기는 어렵습니다.

**요슈아 벤지오(Yoshua Bengio)**는 RBM을 비롯한 비지도학습 기법을 활용하여 심층 신경망을 효과적으로 학습시키는 방법을 연구하고 발전시켰습니다.

## 2. 주요 연구자와 기여

| 연구자 | 주요 기여 |
|---|---|
| 제프리 힌턴(Geoffrey Hinton) | 볼츠만 머신 및 RBM 학습 연구, 대조발산(Contrastive Divergence) 알고리즘, DBN 발전 |
| 테리 세이노프스키(Terry Sejnowski) | 힌턴·애클리와 함께 초기 볼츠만 머신 연구(1985) |
| 데이비드 애클리(David Ackley) | 초기 볼츠만 머신 연구(1985) |
| 요슈아 벤지오(Yoshua Bengio) | RBM·DBN 등 심층 구조의 학습 원리, 층별 비지도 사전학습과 최적화 연구 발전 |

## 3. 힌턴과 벤지오의 연구를 쉬운 예로 비교

### 힌턴: 데이터에 숨어 있는 특징을 어떻게 학습할까?

손글씨 숫자 `3`의 이미지를 RBM에 입력한다고 가정합니다.

1. 가시층(Visible Layer)이 이미지의 픽셀 값을 받습니다.
2. 은닉층(Hidden Layer)이 픽셀 사이의 통계적 관계를 학습합니다.
3. 곡선과 같은 특징을 표현하는 은닉 단위가 만들어질 수 있습니다.
4. 대조발산(CD)은 관측 데이터와 모델이 재구성·생성한 데이터의 통계량 차이를 이용해 가중치를 근사적으로 갱신합니다.

### 벤지오: 이러한 특징 학습을 여러 층으로 확장하면?

여러 층을 차례로 학습하면 점점 추상적인 특징을 표현할 수 있습니다.

```text
입력: 손글씨 숫자 이미지
          ↓
1층 특징 학습: 선과 곡선
          ↓
2층 특징 학습: 선과 곡선의 조합
          ↓
상위 특징 표현: 숫자를 구별하는 데 유용한 패턴
          ↓
분류층: 숫자 예측
```

이 그림은 **계층적 특징 학습을 설명하기 위한 개념적 예시**입니다. 모든 RBM이나 DBN에서 반드시 이러한 특징이 순서대로 나타난다는 의미는 아닙니다.

## 4. 벤지오의 논문과 RBM의 관계

**논문:** *Learning Deep Architectures for AI* — Yoshua Bengio

이 논문은 RBM의 최초 제안 논문이 아닙니다. 주요 논점은 다음과 같습니다.

- 얕은 구조가 복잡한 함수를 효율적으로 표현하기 어려울 수 있는 이유
- 여러 층을 거치며 추상적인 **분산 표현(Distributed Representation)**을 학습하는 이유
- RBM과 **대조발산(CD)**을 통한 비지도 특징 학습
- RBM을 바탕으로 한 **심층 신뢰 신경망(DBN)**과 층별 사전학습
- **적층 오토인코더(Stacked Autoencoder)**를 이용한 대안적 사전학습
- 사전학습 후 **미세조정(Fine-tuning)**을 통한 성능 개선
- 심층 신경망 최적화의 어려움과 점진적 최적화 방법의 가능성

## 5. 핵심 정리

> **힌턴은 RBM·대조발산·DBN의 핵심 기술을 발전시킨 연구자이며, 벤지오는 이를 포함한 심층 학습의 표현·학습·최적화 원리를 체계적으로 연구한 연구자입니다.**

### 참고 문헌

1. Ackley, D. H., Hinton, G. E., & Sejnowski, T. J. (1985). *A Learning Algorithm for Boltzmann Machines.* Cognitive Science.
2. Hinton, G. E. (2002). *Training Products of Experts by Minimizing Contrastive Divergence.* Neural Computation.
3. Hinton, G. E., Osindero, S., & Teh, Y.-W. (2006). *A Fast Learning Algorithm for Deep Belief Nets.* Neural Computation.
4. Bengio, Y. *Learning Deep Architectures for AI.* 업로드한 논문.
