# AIFFEL Campus Online 5th Code Peer Review Templete
- 코더 : 맹선재 (김석영, 조준규, 최예나)
- 리뷰어 : 박혜원


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [O] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  > 네 동작에 이상이 없었고, Rubric 에 명시된 사항들을 전부 아주 잘 수행하셨습니다. 
- [O] 주석을 보고 작성자의 코드가 이해되었나요?
  > 네. 목차 및 각 기능 구현에 따라 코드 블럭들을 나누어 주셔서 확인하기 편했습니다.  
- [O] 코드가 에러를 유발할 가능성이 없나요?
  > 네 없습니다. 
- [O] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 네. 모델 구현 과정에서 구체적인 설명과 주석이 달려있으므로 제대로 이해하고 작성하였다고 생각됩니다. 
- [O] 코드가 간결한가요?
  > 네. 각각의 기능에 대해서만 잘 구현해주셨습니다. 
- [O] 주석을 보고 작성자의 코드가 이해되었나요?

# 제안 
class Discriminator 부분 아래와 같이 수정 
: class Discriminator 부분을 좀더 간결하게 작성하기 위해서 아래와 같이 for 문을 사용하여 구현하는 방식을 제안드립니다. 
코드 간략화 작업을 시행한 부분 (class Discriminator(Model))
```python

class Discriminator(Model):
    def __init__(self):
        super(Discriminator, self).__init__()

        filters = [64,128,256,512,1]
        self.blocks = []
        for i, f in enumerate(filters):
            if i < 3:
                if i == 0:
                    self.blocks.append(DiscBlock(f, stride=2, custom_pad=False, use_bn=False, act=True))
                else:
                    self.blocks.append(DiscBlock(f, stride=2, custom_pad=False, use_bn=True,act=True))
            elif i == 3:
                  self.blocks.append(DiscBlock(f, stride=1, custom_pad=True, use_bn=True, act=True))
            else:
                  self.blocks.append(DiscBlock(f, stride=1, custom_pad=True, use_bn=False,act=False))
        self.sigmoid = layers.Activation("sigmoid")


    def call(self, x, y):
        out = tf.concat([x, y], axis=-1)  # 입력 데이터를 합칩니다.
        for block in self.blocks:
            out = block(out)
        return self.sigmoid(out)


    def get_summary(self, x_shape=(256,256,3), y_shape=(256,256,3)):
        x, y = Input(x_shape), Input(y_shape)
        return Model((x, y), self.call(x, y)).summary()

```


