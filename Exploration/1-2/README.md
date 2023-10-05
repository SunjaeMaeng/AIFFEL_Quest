# AIFFEL Campus Online 5th Code Peer Review Templete
- 코더 : 맹선재
- 리뷰어 : 홍서이


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [O] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  > 주어진 목표인 Project1의 MSE 3000이하 달성, RMSE 150이하 달성을 각각 2722, 121로 모두 만족하였습니다.

- [O] 주석을 보고 작성자의 코드가 이해되었나요?
  > 매 셀마다 상세하게 주석을 달아 주셔서 쉽게 이해할 수 있었습니다.

- [X] 코드가 에러를 유발할 가능성이 없나요?
  > 프로젝트1의 (5)의 model 함수에서 for문을 돌릴때 range(10)으로 설정하였는데 데이터의 feature 개수가 변할 경우 오류가 발생할 수 있습니다.

- [O] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > LMS에 나온 코드 외에도 여러 활용방식(?)을 적용하였습니다. 예를 들어 Project 2의 (3)에서 그래프를 배치할 때 axes를 사용하여 그래프를 배치하였습니다.

- [X] 코드가 간결한가요?
  > Project1의 9번 문제를 해결할 때 동일한 코드를 여러번 작성하였습니다.


```python
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

```python
#(5) 모델 준비하기
# #입력 데이터 개수에 맞는 가중치 W와 b를 준비해주세요.
# Feature의 갯수가 10개 (w = 10, b = 1)
print(train_x.shape)
dim_x = df_x.shape[1] # x의 feature 개수로 설정

w = np.random.rand(dim_x)
b = np.random.rand(1)

print(w.shape, b.shape)

#모델 함수를 구현해주세요.
def model(x, w, b):
    predictions = 0
    for i in range(dim_x):
        predictions += x[:, i] * w[i]
    predictions += b
    return predictions
```
