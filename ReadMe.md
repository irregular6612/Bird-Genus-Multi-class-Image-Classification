# Bird Genus Multi-class Image Classification

## 프로젝트 소개
이 프로젝트는 다양한 새 이미지를 입력받아 해당 새의 속(genus)을 분류하는 딥러닝 기반 이미지 분류 모델을 구현합니다. PyTorch 등 최신 딥러닝 프레임워크를 활용하며, 데이터 전처리, 모델 학습, 평가, 추론까지의 전체 파이프라인을 제공합니다.

## 데이터 구조 및 준비
- 데이터셋은 다음과 같은 구조를 가집니다:
  ```
  images/
    train/
      genus1/
        img1.jpg
        img2.jpg
        ...
      genus2/
        ...
    test/
      img101.jpg
      img102.jpg
      ...
  train.csv
  test.csv
  sample_submission.csv
  ```
- `train.csv`, `test.csv` 파일에는 이미지 파일명과 레이블 정보가 포함되어 있습니다.
- 데이터셋은 별도로 제공되며, `images/` 폴더에 압축을 해제해 주세요.

## 설치 방법
1. 저장소를 클론합니다.
   ```bash
   git clone https://github.com/irregular6612/Bird-Genus-Multi-class-Image-Classification.git
   cd Bird-Genus-Multi-class-Image-Classification
   ```
2. 필요한 패키지를 설치합니다.
   ```bash
   pip install -r requirements.txt
   ```

## 사용 방법
### 1. 학습
```bash
python train.py --config configs/default.yaml
```
- `configs/default.yaml`에서 하이퍼파라미터, 데이터 경로 등을 설정할 수 있습니다.

### 2. 평가
```bash
python evaluate.py --model checkpoints/best_model.pth
```
- 학습된 모델을 불러와 검증/테스트셋에 대해 평가합니다.

### 3. 추론/예측
```bash
python predict.py --input_dir images/test/ --output_file submission.csv
```
- 테스트 이미지에 대해 예측 결과를 생성합니다.

### 4. 결과 예시
- `submission.csv` 파일이 생성되며, 각 이미지에 대한 예측 결과가 저장됩니다.

## 폴더/파일 구조 설명
- `images/` : 학습/테스트 이미지 데이터
- `train.csv`, `test.csv` : 이미지와 레이블 정보
- `checkpoints/` : 학습된 모델이 저장되는 폴더
- `logs/` : 학습 및 평가 로그 파일
- `configs/` : 하이퍼파라미터 등 설정 파일
- `train.py` : 모델 학습 스크립트
- `evaluate.py` : 모델 평가 스크립트
- `predict.py` : 추론/예측 스크립트
- `requirements.txt` : 필요 패키지 목록

# Error or warning Log
#1. UserWarning: The default value of the antialias parameter of all the resizing transforms 
(Resize(), RandomResizedCrop(), etc.) will change from None to True in v0.17, 
in order to be consistent across the PIL and Tensor backends. 
To suppress this warning, directly pass antialias=True (recommended, future default), 
antialias=None (current default, which means False for Tensors and True for PIL), 
or antialias=False (only works on Tensors - PIL will still use antialiasing). 
This also applies if you are using the inference transforms from the models weights: 
update the call to weights.transforms(antialias=True).

#2. 
#3. 

## 기여 방법
1. 이슈를 생성하거나 기존 이슈에 참여해 주세요.
2. 기능 추가, 버그 수정 등은 Pull Request로 기여할 수 있습니다.
3. 코드 스타일 및 커밋 메시지는 일관성을 유지해 주세요.

## 라이선스
이 프로젝트는 MIT 라이선스 하에 배포됩니다.