---
layout: post
title:  "논문 요약"
---

# real-time purchase behavior recognition system based on deep-learning-based object detection and tracking for an unmanned product cabinet

---

# Abstrct

- 멀티카메라
- 불필요한 frame 제거
- real-time integrated system을 만듬
- 성능 잘 나옴

[gpu](https://www.notion.so/gpu-e292660e92c34b9697eca8d5be6deb3f)

# 1. Introduction

- CNN의 발달과 무인 시스템의 많은 사용
- 우리는 computer vision 만 사용 (멀티카메라)
    - 문제점 1 : 여러 카메라를 통한 인식 + tracking 의 어려움
    - 문제점 2 : 여러 비디오를 통한 frame 별 객체인식은 계산이 무거움
- 따라서 real-time cabinet object detection (RCOD) 시스템을 제안함
    - 많은 연산 해결
        - 멀티 카메라의 비디오들을 synchronize하고 change detection (CD)를 통한 frame 선별
        - 선별한 frame에서 object dectect와 tracking을 하고 구매 행동을 파악
- RCOD 시스템의 기여
    - 실시간 application을 위한 통합 시스템을 realized함
    - 새롭게 네트워크를 redesing 함
        - SSD200 in step2
        - RCOD-SSD in step3
    - RCOD 시스템이 현재의 기술로 구현된 최적의 framework임을 입증함

  

# 2. Related works

- 2.1 Recent trend of object detection
    - Faster RCNN 의 등장 → two stage라 실시간 application에는 느림
    - YOLO 와 SSD 의 등장 → SSD 성능 좋음 따라서 SSD 사용했음
- 2.2 Object detection and tracking in a multi-camera system
    - 여러 카메라 view를 통해서, view가 겹칠 때 카메라의 기하학적 정보를 이용하여 
    3D 정보를 만듬 (Houssineau, Clark, Ivekovic, LEE & Franko , 2016)
    - 여러 다른 뷰에서의 identify와 track 이 중요함
        - construct algorithm (robust to defromation of objects)
        (Joo Simon & Seikh, 2018)
        - structure information (Lee et al., 2018)
- 2.3 practical applications of object detection and tracking
    - 실생활에 많이 사용됨 , 무인 어렵지만 RCOD는 잘함

[제목](https://www.notion.so/17145e19c3b247c3aed1c0ebd63b5de2)

# 3. Overview of the proposed algorithm

- RCOD의 3가지 특성
    1. 멀티 카메라를 통한 인식률 증가 및 여러 선반에서의 인식을 동시에 가능
    2. selected frame 만 보기에 연산 빠르게 가능
    3. RCOD기반의 구매행동 인식 시스템을 구현하여 다양한 구매 시나리오에 대해서 
    잘 동작하는지 확인하였움.

![Untitled](real-time%20purchase%20behavior%20recognition%20system%20bas%202aa9489a15a147b39917a218ce432909/Untitled.png)
