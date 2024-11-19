# yolov5_report_final
# Nvidia AI Specialist Certification

---

## **주제: YOLOv5를 이용한 물체의 추락 위험 방지를 위한 안전 감지 시스템 개발 (DropShield system)**

---

## **프로젝트 개요 (OverView of the Project):**

- **배경 정보 소개(Opening Background Information)**:

최근, 다양한 산업 및 가정 환경에서 물체의 안전을 자동으로 감지하고 관리하는 기술의 필요성이 증가하고 있다. 특히, 물체가 탁자나 책상 등의 가구 위에 놓여 있을 때, 지정된 안전 공간을 벗어나면 추락 사고가 발생할 위험이 크다. 이러한 사고는 가정, 상업 공간, 공사장 등에서 빈번하게 발생하며, 그로 인해 물리적 손상이나 인명 피해를 초래할 수 있다. 따라서, 물체의 위치를 실시간으로 감지하고, 추락 위험이 있을 경우 이를 경고하는 시스템이 필요하다. 이러한 기술은 물체가 안전 공간을 벗어나는 것을 방지하고, 다양한 환경에서 사고를 예방하는 데 중요한 역할을 할 수 있다.

- **프로젝트의 전반적인 설명 (General Description of the Current Project):**

이 프로젝트는 물체의 추락 위험을 실시간으로 감지하고 경고하는 안전 감지 시스템을 개발하는 것을 목표로 한다. YOLOv5와 같은 딥러닝 기술을 활용하여 탁자나 책상 등 가구 위에 놓인 물체를 인식하고, 물체가 지정된 안전 공간을 벗어날 경우 이를 감지하여 사용자에게 경고를 제공한다. 이 시스템은 물체의 위치를 실시간으로 모니터링하고, 위험 상황을 조기에 감지하여 추락 사고를 예방하는 데 중점을 둔다. 최근 스마트 기술의 발전과 안전 관리의 필요성이 증가하는 가운데, 이 시스템은 가정, 상업 공간, 공사장 등 다양한 환경에서 안전을 증진시키는 데 기여할 것이다.

- **제안하고 싶은 프로젝트의 강점 (Proposed Idea for Enhancements to the Project):**
1. **실시간 물체 인식과 위험 감지**: YOLOv5를 사용하여 물체를 실시간으로 인식하고, 지정된 안전 공간을 벗어날 경우 이를 즉시 감지하여 경고를 제공할 수 있습니다. 이는 빠르게 변화하는 환경에서도 높은 정확도로 물체를 추적하고 위험을 사전에 예방하는 데 중요한 역할을 합니다.
2. **다양한 환경에 대한 적용 가능성**: 이 시스템은 가정, 상업 공간, 공사장 등 여러 환경에서 적용할 수 있는 유연성을 가지고 있습니다. 물체의 종류와 환경에 관계없이 높은 정확도로 인식할 수 있으며, 추가적인 환경이나 기능을 고려하여 시스템을 확장할 수 있는 장점이 있습니다.

- **프로젝트의 가치와 중요성 ( Value and Significance of this Project):**

물체 추락 방지 시스템은 가정, 상업 공간, 공사장 등에서 발생할 수 있는 물체 추락 사고를 예방하는 중요한 역할을 한다. 이 시스템은 실시간으로 물체를 감지하고 위험을 경고함으로써 인명 피해와 물적 손실을 최소화할 수 있다. 특히, 주방, 공사장, 산업 현장에서는 물체가 추락할 경우 심각한 사고로 이어질 수 있기 때문에, 사고를 예방하는 기술의 도입은 매우 중요하다.

이 프로젝트는 스마트 기술을 기반으로 하여 물체 안전 관리의 효율성을 높이고, 다양한 환경에서 적용 가능한 시스템을 제공한다. 이를 통해 사람들의 안전을 증진시키고, 물체 추락으로 인한 사고를 줄여 사회적 비용을 절감하는 데 기여할 수 있다. 또한, 이 시스템은 향후 스마트 홈, 스마트 공장 등 다양한 IoT 기반 환경에서의 안전 관리 기술 발전에 중요한 역할을 할 것이다.

- **직면하고 있는 한계 (Current Limitations):**
1. **환경 변화에 대한 민감도**: YOLOv5 기반의 물체 인식 시스템은 다양한 환경에서 높은 정확도를 보이지만, 조명, 물체의 크기나 형태, 그리고 배경이 복잡한 환경에서는 인식 정확도가 떨어질 수 있다. 이러한 환경 변화에 대해 시스템의 강인성을 높이기 위한 추가적인 데이터 학습과 모델 개선이 필요하다.
2. **실시간 처리 성능의 한계**: 물체 인식 및 위험 감지 시스템은 실시간으로 데이터를 처리해야 하므로, 처리 속도와 성능이 중요한 요소로 작용한다. 현재의 모델이 높은 정확도를 제공하지만, 실시간 환경에서의 처리 속도 개선이 필요하며, 다양한 하드웨어 환경에서의 최적화가 요구된다.

- **문헌 고찰 (Literature Review):**

이 프로젝트를 위해 YOLOv5를 활용하는 데 있어, 관련 기술과 최신 연구 동향을 조사하고 있다. YOLOv5는 물체 인식 분야에서 우수한 성능을 보이며, 다양한 환경에서의 적용 가능성에 대한 여러 연구들이 존재한다. 이러한 연구들을 통해 YOLOv5의 정확도와 실시간 처리 능력에 대한 정보와 함께, 환경 변화에 대한 유연성을 높이는 방법을 탐구하고 있다. 또한, 물체 추락 위험을 감지하는 시스템에 대한 기존 연구들을 분석하여, 이 프로젝트의 기술적 기반을 다지고, 보다 효율적이고 실용적인 시스템을 설계하기 위한 방향을 설정하고 있다. 이를 바탕으로 실제 환경에서의 물체 인식과 위험 감지 성능을 최적화할 수 있는 방법을 모색하고 있다.

---

## **영상 취득 방법 (Image Acquisition Method):**

이 프로젝트에서는 물체의 추락 위험을 감지하기 위해, 집에서 직접 물체를 다양한 방향으로 이동시키며 영상을 취득하였다. 물체는 탁자, 책상 등의 가구 위에 놓인 상태에서 추락 위험이 있는 위치로 이동시켜, 추락 사고를 유발할 수 있는 다양한 상황을 재현하였다.

### 실제 환경에서의 물체 추락 위험 영상

https://youtube.com/shorts/nn1UpF9YRS8?feature=share

---

## 학습 데이터 추출과 학습 어노테이션 (**Learning Data Extraction and Learning Annotation)**:

### 비디오 해상 조정 (Video resolution adjustment)

YOLOv5에서 640 해상도 이미지로 학습하기 위해서 영상을 640 x 640 해상도 영상으로 만들었다.  

https://online-video-cutter.com/ko/resize-video

### DarkLabel

640 x 640 해상도로 만들어진 영상을 프레임 단위로 이미지로 만들거나 어노테이션을 하기 위해서 Video/Image Labeling and Annotation Tool로 잘 알려진 DarkLabel을 사용했다.

- **데이터 추출**: 수집한 영상을 **DarkLabel** 에서 이미지로 추출합니다.

https://drive.google.com/drive/folders/1BdAVD2W8ULQyGreOrrF9u8lwIlxFq0LN?usp=drive_link

![image](https://github.com/user-attachments/assets/c3c9f044-fa2b-4089-9d81-a2a8b19cf3ab)

1. 먼저 Annotation을 하기 전에 darklabel.yml을 통해 classes를 추가한다.

```jsx
my_classes1: ["lane", "vehicle", "bicycle", "motorbike", "animal", "tree", "building"]
my_classes2: ["cup"]
```

```jsx
format1:    # darknet yolo (predefined format]
  fixed_filetype: 1                 # if specified as true, save setting isn't changeable in GUI
  data_fmt: [classid, ncx, ncy, nw, nh]
  gt_file_ext: "txt"                 # if not specified, default setting is used
  gt_merged: 0                    # if not specified, default setting is used
  delimiter: " "                     # if not spedified, default delimiter(',') is used
  classes_set: "my_classes2"     # if not specified, default setting is used
  name: "darknet yolo"           # if not specified, "[fmt%d] $data_fmt" is used as default format name
```

DarkLabel 프로그램에 darknet yolo라는 classes가 추가 되었고 밑에 한 개의 ‘cup’ class가 추가된 것을 확인할 수 있다.

1. DarkLabel에서  image를 불러와서 해당 class에 부합하는 물체를 라벨링 한다.

DarkLabel에서 Open Image Folder를 통해 images 폴더를 선택하여 변환된 이미지를 불러왔다. Box + Label로 선택 후 아래 사진과 같이 해당 class에 부합하는 물체에 Annotation을 했다. Annotation이 끝난 후 GT Save As를 통해 cup이라는 폴더를 만들고 해당 폴더 안에 저장 했다.

![스크린샷 2024-11-15 004325](https://github.com/user-attachments/assets/369fcbd1-fbac-4c36-a41a-4f386eecca52)

1. cup 폴더 안에 라벨링 된 txt파일이 있음을 확인할 수 있다. 

![스크린샷 2024-11-15 004713](https://github.com/user-attachments/assets/9b0f07d2-ec79-456c-b469-68ddc7ee7f57)

### dataset_DropShield

구글 드라이브에 학습 데이터셋과 관련 파일들을 업로드하였습니다. 

[[DropShield 프로젝트 데이터셋](https://drive.google.com/drive/folders/1Bk9CTE8Io8aZy_ghK3eAe5coI59dylW7?usp=drive_link)](https://www.notion.so/DropShield-2eb917091520494da6b309ad98008b7b?pvs=21)

이 폴더에는 다음과 같은 내용이 포함되어 있습니다:

- 학습용 이미지 파일 cup_000
- 라벨링 된 데이터 cup

---

## Nvidia Jetson Nano 학습 과정:

### 구글 드라이브 연동

`drive.mount('/content/drive')` 명령어를 통해 구글 드라이브를 Colab 환경에 마운트하여, 드라이브 내의 파일에 접근하고 사용할 수 있도록 설정한다.

```jsx
from google.colab import drive
drive.mount('/content/drive')
```

### yolov5 설치

다음은 YOLOv5 모델을 GitHub에서 클론하고, 필요한 라이브러리를 설치하는 과정이다.

```jsx
#clone YOLOv5 and
!git clone https://github.com/ultralytics/yolov5  # clone repo
%cd yolov5
%pip install -qr requirements.txt # install dependencies

!pip install Pillow==10.3
```

`!git clone` 명령어로 YOLOv5 리포지토리를 클론

`%pip install -qr requirements.txt`를 통해 YOLOv5 실행에 필요한 라이브러리들을 자동 설치

`Pillow==10.3` 버전을 설치하여 이미지 처리에 필요한 기능을 제공

### 이미지 파일 관리

1. 먼저, YOLOv5 모델 학습을 위한 데이터 폴더 구조를 생성한다.

```
!mkdir -p Train/labels
!mkdir -p Train/images
!mkdir -p Val/labels
!mkdir -p Val/images
```

`Train` 폴더 → 학습용 이미지와 레이블 파일을 저장하는 디렉토리

`Val` 폴더 → 검증용 이미지와 레이블 파일을 저장하는 디렉토리

1. 각각의 하위 폴더에 이미지와 해당 레이블 데이터를 구분하여 업로드 한다.

![스크린샷 2024-11-15 011608](https://github.com/user-attachments/assets/63cf7556-313a-44ac-ba83-e0e8e808867f)

1. yolov5 폴더에 가이드와 함께 제공된 **yolov5n.pt** 파일과 라벨링한 class의 이름에 맞게 수정한 **data.yaml** 파일을 업로드 한다.

### yolov5 모델 학습

1. 이미지 전처리 및 데이터셋 생성
- `torch`, `os`, `IPython.display`, `numpy`, `tensorflow`, `PIL` …
    
    다양한 라이브러리를 불러와서 이미지 처리, 데이터셋 관리, 출력 등을 수행한다. 
    
- `_preproc()`
    
    이미지를 리사이즈 하고 중앙에서 크롭하여 모델 입력에 맞는 크기로 변환한다.
    
- `Create_npy()`
    
    지정된 디렉토리에서 이미지를 불러와 전처리 후 `npy` 파일 형식으로 저장한다.
    

1. 모델 학습에 필요한 이미지 데이터 준비

```jsx
Create_npy('/content/drive/MyDrive/yolov5/Train/images', 512, 'jpg')
```

1. 모델 학습

```jsx
!python train.py  --img 512 --batch 16 --epochs 300 --data /content/drive/MyDrive/yolov5/data.yaml --weights yolov5n.pt --cache
```

- `train.py` 스크립트를 사용하여 YOLOv5 모델을 학습시킨다.
- `--img 512` 옵션을 통해 입력 이미지 크기를 512로 설정하고, `--batch 16`으로 배치 크기를 설정하여 모델 학습을 진행한다.
- `--epochs 300`으로 총 300번의 학습 epoch을 설정하고, `--data` 옵션을 통해 데이터셋 경로를 지정했다.
- 사전 훈련된 `yolov5n.pt` 가중치를 사용하여 초기 모델 가중치를 설정한다.

<aside>
💡

**yolov5 모델 학습 완료**

</aside>

![스크린샷 2024-11-15 013046](https://github.com/user-attachments/assets/74813eb8-11e3-4600-af32-f0674feb6460)

 yolov5 폴더 안 runs/train/exp에 물체가 학습된 걸 확인할 수 있다.

### yolov5 모델 학습 결과 검증

학습 결과는 다음과 같다.

https://drive.google.com/drive/folders/1fdNvyTpTAPEKfL-fzqJbzyR3yTY0g1Fl?usp=sharing

![스크린샷 2024-11-15 020503](https://github.com/user-attachments/assets/1f1082e3-a46a-4b32-82af-9d589e059d75)

![confusion_matrix (2)](https://github.com/user-attachments/assets/f53e0d04-f2b1-42ae-8da2-5acac80db3d9)

![labels_correlogram](https://github.com/user-attachments/assets/82ac50f1-22aa-49f2-a8ec-144b2159427b)

![labels](https://github.com/user-attachments/assets/c546758d-d4c3-4e4e-8cfa-6225f2b87735)

### F1_Curve

![F1_curve](https://github.com/user-attachments/assets/9878a91a-7057-4846-8b44-90656fdf601a)

### P_Curve

![P_curve](https://github.com/user-attachments/assets/a14cf5cf-0755-48a2-b0f2-81fa513547cb)

### PR_Curve

![PR_curve](https://github.com/user-attachments/assets/450daf26-5e2c-437a-83b2-1ce3e5a8a824)

### R_Curve

![R_curve](https://github.com/user-attachments/assets/bbe85cb7-bb51-43ce-8b68-d74259367a5d)

### Results

![results](https://github.com/user-attachments/assets/e9fa1f6b-b381-439f-88b2-37d98761299f)

### train_batch

![train_batch0](https://github.com/user-attachments/assets/b765e1ab-8f56-4959-b3f3-3310a504c62f)

### val_batch

![val_batch0_labels](https://github.com/user-attachments/assets/7d7dbb82-3068-4497-a452-3787846fe8a1)

### **학습 결과 확인**

학습 후 학습 결과를 확인하기 위한 작업이 필요하다. exp파일 안에 weights 파일이 있다.

그 중 `best.pt` 를 활용하여 `detect.py`를 진행해 학습 결과를 확인한다.

```jsx
!python detect.py --weights runs/train/exp/weights/best.pt --img 512 --conf 0.1 --source /content/drive/MyDrive/yolov5/Train/images
```

- **`-weights`**: 훈련된 모델 가중치 파일(`best.pt`)을 사용.
- **`-img 512`**: 입력 이미지 크기를 512x512로 설정.
- **`-conf 0.1`**: 감지된 객체의 신뢰도 임계값을 0.1로 설정.
- **`-source`**: 감지할 이미지가 있는 폴더 경로를 지정 (`/content/drive/MyDrive/yolov5/Train/images`)

### **detect.py 실행 이미지 (detect.py execution image):**

![스크린샷 2024-11-15 024009](https://github.com/user-attachments/assets/bd88c470-d618-4521-9191-e93b49e06d15)

감지 결과는 `runs/detect/exp2` 폴더에 저장 된 것을 확인 할 수 있다.

### **detect.py를 통한 학습 결과 (Learning outcomes with detect.py):**

![val_batch0_pred](https://github.com/user-attachments/assets/27ce7ab3-fb1d-4771-a9e1-414f24d51ae8)


![val_batch2_pred](https://github.com/user-attachments/assets/00fb3e7d-59b9-408f-bebe-379e7a1461c8)


![val_batch1_pred](https://github.com/user-attachments/assets/2bc3d954-8b53-44ba-9770-4f41af9bf183)

### **detect.py 실행 영상**

```jsx
!pip install ultralytics

!python3 /content/drive/MyDrive/yolov5/detect.py --weights /content/drive/MyDrive/yolov5/runs/train/exp/weights/best.pt --source /content/drive/MyDrive/cup.mp4
```

![스크린샷 2024-11-15 122412](https://github.com/user-attachments/assets/5562a70b-6e8f-464f-af4c-5b4567e94be0)

https://youtube.com/shorts/34_5k8nfyI4

![스크린샷 2024-11-15 030047](https://github.com/user-attachments/assets/ffada41f-ab9d-456c-9a05-d34ed9394c66)
