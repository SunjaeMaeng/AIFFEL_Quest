# AIFFEL Campus Online 5th Code Peer Review
- 코더 : 맹선재 (조준규, 김석영)
- 리뷰어 : 신유진


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [ ] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  > 마지막 step5 부분이 너무 아쉽게도 미완성이다, 시간이 더 있었다면 충분히 해결하셨을거로 보인다.
- [X] 주석을 보고 작성자의 코드가 이해되었나요?
  > flow별로 주석이 잘 정리되어있다.
- [X] 코드가 에러를 유발할 가능성이 없나요?
  > 마지막 step5부분은 에러가 발생하는데, 이는 당사자들도 왜 그런지 파악하고 있다. 따라서 항목을 체크한다.
- [X] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 코드 작동 원리를 이해하고 있고, 이를 주석으로도 표시해놨고, 에러가 발상하는 부분에서 개선방안도 알고 있다.
- [X] 코드가 간결한가요?
  > 넵!

  > 

# 예시
```python
# lambda함수를 활용해 text와 headlines를 한번에 넣을 수 있는 방법을 제안

urllib.request.urlretrieve("https://raw.githubusercontent.com/sunnysai12345/News_Summary/master/news_summary_more.csv", filename="news_summary_more.csv")

# 본 코드에는 'text_list'에 할당했는데 csv를 불러올때는 df형태로 불러오므로 list라는 단어가 포함된 변수로 할당할시 헷갈릴수 있다.
summa_df = pd.read_csv('news_summary_more.csv', encoding='iso-8859-1')
summa_df.tail() # head()로 불러올 수 있지만 나는 보통 데이터 (row)개수가 총 몇개인지를 파악하기 위해 tail()로 쓰는 것을 선호한다.

# 먼저 summa_df로 불러온 후 text컬럼에 있는 데이터를 리스트로 옮기고, 옮길때 각 요소들은 str형태로 담기도록 한다. 그래야 뒤에 Abstract요약 뽑아내는 부분에서 str형태로 출력이 된다. 
text_sum = []
for text in summa_df['text']:
    text_sum.append(str(text))

# summa_df에 담긴 데이터를 비율을 0.5로 둬서 summary로 바꿔본다. 비율을 0.0005로 했을때 (당연한 원리지만) text의 양이 적어져서 summary로 할당이 안된다. lambda 함수를 활용해 볼 수 있을 거 같다.
summa_df['summary'] = summa_df['text'].apply(lambda x: summarize(x, ratio=0.5))

# text가 summary안에 잘 들어갔는지 확인용
summa_df['summary'].sample(10)  


# 실제 요약과 추출된 요약 비교, 윗 상태가 되어야 for문에 들어갔을때 문제없이 출력됐었다..! (여러번 에러난 후 깨닫게 됨)
for i in range(10):
    print("원문 :", summa_df['text'][i])
    print("실제 요약 :", summa_df['headlines'][i])
    print("추출 요약 :", summa_df['summary'][i])
    print("\n")

```



# 참고 링크 및 코드 개선
위에서 코드 개선을 진행해서 이 칸은 skip하겠음



