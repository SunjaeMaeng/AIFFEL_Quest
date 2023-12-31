# AIFFEL Campus Online 5th Code Peer Review
- 코더 : 맹선재
- 리뷰어 : 최철웅


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [X] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  - 한 인물만 존재하는 사진에서 얼굴 인식, 랜드마크, 스티커 붙이기 모두 정상 작동
- [X] 주석을 보고 작성자의 코드가 이해되었나요?
  - 주석이 코드의 각 부분이 어떤 역할과 동작을 하는지 상세하게 설명해줌
- [X] 코드가 에러를 유발할 가능성이 없나요?
  - 연산하면서 중간 결과물이 어떻게 나오는지 확인함
- [X] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  - 주석을 통해 해당 코드를 이해하는데 필요한 지식도 서술함
- [X] 코드가 간결한가요?
  - 역할에 따라 코드 블록을 잘 나눔
  - 반복적인 코드가 없음
- [X] 주석을 보고 작성자의 코드가 이해되었나요?
  - 해당 코드가 어떻게 돌아가는지 상세하게 설명해둠
  - 특정 함수가 어떤 동작을 하는지를 설명함

# 예시
1. 코드의 작동 방식을 주석으로 기록합니다.
2. 코드의 작동 방식에 대한 개선 방법을 주석으로 기록합니다.
3. 참고한 링크 및 ChatGPT 프롬프트 명령어가 있다면 주석으로 남겨주세요.
- [ ] 주석을 보고 작성자의 코드가 이해되었나요?
- [ ] 코드가 에러를 유발할 가능성이 없나요?
  > 

- [ ] 코드가 에러를 유발할 가능성이 없나요?

- [ ] 코드 작성자가 코드를 제대로 이해하고 작성했나요?

- [ ] 코드가 간결한가요?
- [ ] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 

- [ ] 코드가 간결한가요?
  > 


```python
# 사칙 연산 계산기
class calculator:
    # 예) init의 역할과 각 매서드의 의미를 서술
    def __init__(self, first, second):
        self.first = first
        self.second = second

    # 예) 덧셈과 연산 작동 방식에 대한 서술
    def add(self):
        result = self.first + self.second
        return result

a = float(input('첫번째 값을 입력하세요.')) 
b = float(input('두번째 값을 입력하세요.')) 
c = calculator(a, b)
print('덧셈', c.add()) 
#(5) 모델 준비하기
# #입력 데이터 개수에 맞는 가중치 W와 b를 준비해주세요.
# Feature의 갯수가 10개 (w = 10, b = 1)
print(train_x.shape) 
w = np.random.rand(10)
b = np.random.rand(1)

print(w.shape, b.shape)

#모델 함수를 구현해주세요.
def model(x, w, b):
    predictions = 0
    for i in range(10):
        predictions += x[:, i] * w[i]
    predictions += b
    return predictions
```



# 참고 링크 및 코드 개선
```
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```

```python

```
