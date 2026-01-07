# 🚦 YOLOv8 Road Sign Detection
YOLOv8 기반 도로 표지판(Road Sign) 객체 탐지 프로젝트입니다.
Kaggle의 Road Sign Detection 데이터셋을 활용하여 4가지 종류의 도로 표지판을 실시간으로 탐지할 수 있도록 학습했습니다.

## 📊 Project Overview
* **Model**: YOLOv8n (Nano)
* **Epochs**: 20
* **Image Size**: 640
* **Task**: Object Detection
* **Framework**: Ultralytics YOLO, PyTorch

## 🎯 Target Classes
이 모델은 다음 4가지 클래스를 탐지합니다:
1.  **Traffic Light** (신호등)
2.  **Stop** (정지 표지판)
3.  **Speed Limit** (속도 제한)
4.  **Crosswalk** (횡단보도)

## 📈 Performance (Result)
학습 결과 **mAP50 0.95** 이상의 높은 정확도를 보였습니다.

### 📷 Detection Result
학습된 모델을 사용하여 실제 도로 이미지를 테스트한 결과입니다.

![d4473910-a402-4e11-81c3-6c8a621ce130](https://github.com/user-attachments/assets/612fc8b6-b402-4f35-a7f8-bba2967b438d)
![1fa3526e-f289-457a-a5cf-834bdbe6d720](https://github.com/user-attachments/assets/22cbf257-b406-4e5d-b66f-ca2258ab6ef5)
![ec7b4c3a-a9c2-47d4-b273-fab81c857137](https://github.com/user-attachments/assets/ae3d7888-2b35-46c0-8391-c1d0f1933943)

> *위 이미지는 모델이 테스트 데이터셋을 추론한 결과입니다.*

## 💾 Dataset
* **Source**: [Kaggle Road Sign Detection](https://www.kaggle.com/datasets/andrewmvd/road-sign-detection)
* **Structure**:
    * `images/`: 학습 및 테스트 이미지
    * `labels/`: YOLO 포맷 라벨링 데이터 (txt)

## 🚀 How to Run
```python
from ultralytics import YOLO

# 모델 로드
model = YOLO('best.pt')  # 학습된 가중치 파일

# 이미지 예측
results = model.predict(source='test_image.jpg', save=True)
