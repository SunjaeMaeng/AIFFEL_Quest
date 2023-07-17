# AIFFEL Campus Online 5th Code Peer Review
- 코더 : 맹선재
- 리뷰어 : 김민식


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [O] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  - 네. 각 과정에 대해 결과를 잘 보여주고 있습니다.
- [O] 주석을 보고 작성자의 코드가 이해되었나요?
  - 네. 일반적인 Python 주석 외에도 markdown을 활용하여 각 단계를 잘 설명해주고 있습니다
- [O] 코드가 에러를 유발할 가능성이 없나요?
  - 네. 에러가 있었다면 에러 내역이 있었을것으로 생각됩니다.
  - 현재 모든 코드에서 에러 내역은 없습니다.
- [O] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  - 네. 각 코드가 무얼 위해 동작하는지, 구성되었는지 등을 잘 작성하였습니다.
- [O] 코드가 간결한가요?
  - 네. 이미지를 부르는 부분을 재사용하기 좋게 함수처리하였습니다.
  - def load_img(img_file) 부분
- ~~[O] 주석을 보고 작성자의 코드가 이해되었나요?~~
  - 위 질문과 중복되는것 같아 취소선 처리 해두겠습니다.

  > 위 내용과 별개로 제가 `Step 2.`를 제대로 처리하지 못해 선재님의 처리방식(코드)은 어떤지 궁금하였습니다.
  >> 이 부분에 대해 결과는 잘 확인하였지만 코드 내역이 없어 개인적으로 조금 아쉽습니다.

# 예시
```python
# 모듈화 흔적 첫번째 부분
def load_img(img_file):
    img_path = os.getenv('HOME')+'/aiffel/human_segmentation/images/'
    my_img_path = join(img_path, img_file)
    img_orig = cv2.imread(my_img_path) 

    return img_orig, my_img_path
```



# 참고 링크 및 코드 개선
```
제 코드 기준에서 model을 부를때 이미지 사이즈가 맞지않는 경우가 있어 참고용 resize 코드를 남겨봅니다.

chatGPT를 참고하였습니다.
```

```python
import cv2

# 원하는 크기로 이미지 조정
def resize_image(img, size):
  height, width = size
  resized_img = cv2.resize(img, (width, height))
  return resized_img

# 이미지 읽기
img_orig = cv2.imread(img_path)

# 원하는 크기로 이미지 조정
desired_size = (500, 1000) # 훈련 데이터셋의 이미지 크기에 맞게 조정하세요.
resized_img = resized_image(img_orig, desired_size)

# 조정된 이미지의 크기를 확인합니다.
print(resized_img.shape)
```

