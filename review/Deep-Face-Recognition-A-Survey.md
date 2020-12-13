# Deep Face Recognition: A Survey - Review


### Abstract

---

딥러닝은 다중 처리 레이어(multiple processing layers)를 적용하여 다중 레벨 특징 추출(multiple levels of feature extraction)을 사용한 데이터의 표현을 학습한다.  
이 기술은 Deepface method를 통해 안면 인식(FR; Face Recognition)연구를 재구성하였다.  
이 Survey에서는 알고리즘 설계, 데이터베이스, 프로토콜, 어플리케이션 scenes들을 다루는 deep FR에서 최근 development에 대한 포괄적인 리뷰를 제공한다.

1.  다른 네트워크 구조와 손실 함수(loss functions) 요약
2.  두 가지로 나눠진 face processing methods 요약 및 비교
    -   one-to-many augmentation
    -   many-to-one normalization
3.  잡다한 scenes 리뷰
    -   cross-factor, heterogenous, multiple-media, industry scenes
4.  현재 methods들의 기술적 난제와 몇몇 전도유망한 방향들

### Introduction

---

### Overview

---

A. Background Concepts and Terminology

3가지 모듈이 필요하다.

1.  Face detector : 이미지나 영상의 얼굴을 localize하는데 사용
2.  Facial landmark detector : 얼굴을 정규화된 표준 좌표(canonical coordinates)에 정렬
3.  FR module : 정렬된 얼굴 이미지들로 실행된다.

FR의 분류

-   face verification : 갤러리와 탐색대상(probe) 간 일대일 유사도를 계산하여 두 이미지가 같은 것인지 결정
  
-   face identification : 일대다 유사도를 계산하여 탐색대상이 특정 신원인지 결정
  
    -   closed-set identification : probe가 갤러리 신원 중에 있음
    -   open-set identification : probe가 갤러리에 없는 사람이 있음

B. Components of Face Recognition

FR module에 얼굴 이미지가 입력되기 전, face anti-spoofing(얼굴이 live인지 spoofed인지 확인)하여 여러 유형의 attack들을 피한다. 이것을 FR의 한 scene으로 취급한다. 그러고 나면 인식을 수행한다. FR module은 face processing, deep feature extraction, face matching으로 구성된다.

P는 poses, illuminations, expressions, occlusion과 같은 intra-personal variations를 다루기 위한 face processing을 나타낸다.
