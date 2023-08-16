# AIFFEL Campus Online 5th Code Peer Review
- 코더 : 맹선재
- 리뷰어 : 황인준


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [O] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  - 네 다양한 tokenizer들과 그 변수들을 조정하면서 영화 리뷰 classification수행 능력을 확인했고, 그 accuracy가 목표치인 80%를 모두 넘겼다.
```python
padding='pre'
Unigram 0.8331
KoNLPy 형태소 분석기 0.8312
BPE 0.8297
WORD 0.8262
CHAR 0.8250
padding='post'
KoNLPy 형태소 분석기 0.8278
WORD 0.8226
CHAR 0.7883
BPE 0.6061
Unigram 0.4972
```
- [O] 주석을 보고 작성자의 코드가 이해되었나요?
  - 네 주석을 보고 코드가 어떤 의도에 의해 작성되었는지 확인 가능했습니다.
- [O] 코드가 에러를 유발할 가능성이 없나요?
  - 현재 코드 상으로는 없는것 같습니다
- [O] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  - 네 주석이 제대로 작성된 점, 에러가 없고, 결과또한 목표치에 도달했기에 제대로 이해하고 작성했음을 알 수 있습니다.
- [O] 코드가 간결한가요?
  - 모델 선언하는 부분이나, 그래프 그리는 부분은 여러번 사용하기 때문에 함수화 할 수도 있습니다. 나머지는 간결한것 같습니다.
 

# 참고 링크 및 코드 개선

```python
  class HistoryPlotter:
    def __init__(self, history):
        self.history = history

    def plot(self):
        # Accuracy
        plt.figure(figsize=(12, 4))

        plt.subplot(1, 2, 1)
        plt.plot(self.history.history['accuracy'], label='Train Accuracy')
        plt.plot(self.history.history['val_accuracy'], label='Validation Accuracy')
        plt.legend()
        plt.title('Accuracy')

        # Loss
        plt.subplot(1, 2, 2)
        plt.plot(self.history.history['loss'], label='Train Loss')
        plt.plot(self.history.history['val_loss'], label='Validation Loss')
        plt.legend()
        plt.title('Loss')

        plt.tight_layout()
        plt.show()
```






```python

```


