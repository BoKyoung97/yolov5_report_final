# yolov5_report_final
# Nvidia AI Specialist Certification

---

## **topic: Development of a Safety Detection System to Prevent Object Falls Using YOLOv5 (DropShield System)**

---

## **OverView of the Project:**

- **Opening Background Information**:

In recent years, the demand for technology capable of automatically detecting and managing the safety of objects has significantly increased across various industrial and domestic environments. Objects placed on furniture, such as tables or desks, can fall when moved beyond designated safe areas, leading to accidents. Such incidents are common in households, commercial spaces, and construction sites, causing physical damage or injury. A system capable of real-time detection and alerting users about potential risks is thus critical to preventing these incidents.

- **General Description of the Current Project:**

The objective of this project is to develop a real-time safety detection system to identify and warn against the risk of objects falling. Using YOLOv5, a deep learning technology, the system detects objects placed on furniture and identifies when they move outside predefined safe zones. This system focuses on monitoring the location of objects in real time and detecting hazardous situations early to prevent accidents. It is intended for use in various environments, including homes, commercial spaces, and construction sites, enhancing safety and minimizing potential damages.

- **Proposed Idea for Enhancements to the Project:**
1. **Real-time Object Detection and Hazard Recognition**: By leveraging YOLOv5, the system ensures real-time object detection and immediate recognition when objects leave the safe area, offering early alerts to users.
2. **Versatility Across Diverse Environments**: The system is adaptable to different scenarios, including homes, commercial spaces, and construction sites, with the ability to detect a variety of objects accurately.

- **Value and Significance of this Project:**

The object fall prevention system plays a crucial role in preventing accidents caused by falling objects in various environments such as households, commercial spaces, and construction sites. By detecting objects in real time and issuing warnings about potential risks, the system minimizes human injuries and property damage. This is especially significant in kitchens, construction sites, and industrial settings, where falling objects can lead to severe accidents, making the adoption of preventative technologies essential.

This project leverages smart technologies to enhance the efficiency of object safety management while providing a system adaptable to diverse environments. Through this approach, it aims to improve safety, reduce accidents caused by falling objects, and contribute to lowering societal costs. Furthermore, the system holds the potential to play a pivotal role in advancing safety management technologies in various IoT-based environments, such as smart homes and smart factories, in the future.

- **Current Limitations:**
1. **Sensitivity to Environmental Changes**: While the YOLOv5-based object recognition system demonstrates high accuracy in various conditions, its performance may degrade in environments with poor lighting, objects of varying sizes or shapes, or complex backgrounds. Enhancing the system's robustness against these environmental variations requires additional data training and model improvements.
2. **Limitations in Real-Time Processing Performance**: Object recognition and hazard detection systems must process data in real-time, making processing speed and performance critical factors. Although the current model delivers high accuracy, there is a need to improve its processing speed in real-time environments and optimize it for various hardware platforms.
   
- **Literature Review:**

For this project, we are investigating relevant technologies and the latest research trends related to the application of YOLOv5. YOLOv5 has demonstrated exceptional performance in object recognition and has been the subject of numerous studies exploring its applicability in various environments. Through these studies, we aim to gain insights into YOLOv5’s accuracy, real-time processing capabilities, and strategies to enhance its adaptability to environmental changes. Additionally, by analyzing existing research on systems designed to detect object fall hazards, we are establishing the technical foundation for this project. This approach helps guide the development of a more efficient and practical system. Based on these findings, we are exploring methods to optimize object recognition and hazard detection performance in real-world environments.

---

## **Image Acquisition Method:**

In this project, to detect the risk of object falls, videos were captured by manually moving objects in various directions at home. The objects were placed on furniture such as tables and desks and moved to positions where there was a risk of falling, simulating various scenarios that could potentially lead to fall accidents.

### Videos of object fall risks in real-world environments

https://youtube.com/shorts/nn1UpF9YRS8?feature=share

---

## **Learning Data Extraction and Learning Annotation**:

### Video resolution adjustment

The video was converted into 640 x 640 resolution frames to train the YOLOv5 model with 640 resolution images.

https://online-video-cutter.com/ko/resize-video

### DarkLabel

To create frames from the video at 640 x 640 resolution or to perform annotation, DarkLabel, a well-known Video/Image Labeling and Annotation Tool, was used.

- **data extraction**: The collected video is extracted into images using **DarkLabel**.

https://drive.google.com/drive/folders/1BdAVD2W8ULQyGreOrrF9u8lwIlxFq0LN?usp=drive_link

![image](https://github.com/user-attachments/assets/c3c9f044-fa2b-4089-9d81-a2a8b19cf3ab)

1. 

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

It can be seen that a class called darknet yolo has been added to the DarkLabel program and one 'cup' class has been added at the bottom.

1. Import the image from DarkLabel and label the object that matches the class.

From DarkLabel, the images folder was selected through the Open Image Folder to import the converted image. After selecting Box + Label, an announcement was made on the object that matches the class as shown in the picture below. After the announcement was completed, a folder called cup was created through GT Save As and stored in the folder.

![스크린샷 2024-11-15 004325](https://github.com/user-attachments/assets/369fcbd1-fbac-4c36-a41a-4f386eecca52)

2. You can see that there is a labeled txt file in the cup folder.

![스크린샷 2024-11-15 004713](https://github.com/user-attachments/assets/9b0f07d2-ec79-456c-b469-68ddc7ee7f57)

### dataset_DropShield

Uploading the learning data reset to Google drive.

[[DropShield 프로젝트 데이터셋](https://drive.google.com/drive/folders/1Bk9CTE8Io8aZy_ghK3eAe5coI59dylW7?usp=drive_link)]

This folder contains the following:

- Image file 'cup_000' for learning
- Labeled data 'cup'

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
