## Linear Regression

[참고](https://sshkim.tistory.com/147)

![image-20200902103306533](md_image/image-20200902103306533.png)



![image-20200902103322809](md_image/image-20200902103322809.png)



![image-20200902103428160](md_image/image-20200902103428160.png)



![image-20200902103628622](md_image/image-20200902103628622.png)





## Q & A

@here 09/02(수) 10시 인공지능 도메인 Linear Regression 이해 Q&A

Q1. 저기서 왜 squeare를 하나요? -(한기철 컨설턴트)이차식을 만들어줘야 미분을 사용해서 각 지점에서의 변화량(기울기)를 구할 수 있기도 하고요 => MSE에서 미분 할 경우, 계산이 편하고, 사각형으로 보여 줄 수 있어 이해하기도 편하기 때문에 사용 합니다. 다른 방법으로는 MAE, RMSE 등도 있습니다.

Q2. 러닝메이트를 잘 설정해줘야하나요? -네 잘못 설정하면 최적 값이 아니라 양쪽으로 진동 할 수도 있습니다. -너무 낮으면 오래걸리고 너무 높으면 minimum을 못찾을 수도 있습니다. -너무커도 너무 작아도 안됩니다! 저 밥그릇을 벗어날 수 있 습니다 -보통 그래서 적절한 값을 조절하거나 유사 사례를 통해서 정하는 경우가 많습니다 . => 너무 크면 발산하고, 너무 작으면, 트레이닝 하는데 시간이 많이 걸립니다. 때문에 적잘한 값을 설정 해줘야 하는데, Tensflow 같은 Lib 에서는 적절한 값을 자동으로 설정 해주는 알고리즘이 들어가 있습니다. 

Q3. w는 러닝메이트로 찾아가는거 같은데 그러면 b는 저희가 알아서 찍어줘야하나요 아니면 b도 러닝메이트와 관련된 식이 있나요 => Bias 또한 Weight 동일한 방식으로 찾아 갑니다. Bias에 대한 Cost 함수를 미분한 값과 런닝레이트를 값을 곱한 결과를 반영하면 됩니다. 

Q4. 임계값을 구하는 방법이 따로 있나용? 아니면 경험적으로 찾아가나요? -방금은 mse가 2차 방정식이라 최저점에 맞추는데 Cost Function이 n차원인 경우 지역 최저점을 찾아서 임계점으로 잡는것으로 알고 있습니다 .. => 임계값, 극소값, 최저값 용어의 차이 일 뿐, 동일한 의미 입니다. 어쨋든 N차원 이라도 경사 하강법으로  최저값을 찾아 갑니다.

Q5. 러닝레이트는 어떻게 구해요?? -(실습코치)학습 진행에 따라서 러닝레이트를 낮추거나 높이는 등 변화를 주는 방법도 사용하는 것으로 알고 있습니다. A. 실습코치님이 맞는 답변을 주셨습니다. 실습과정에서 러닝메이트도 조절을 할 수 있는 방법이 있습니다. => Q2와 동일한 답변 

Q6. 위에서 몸무게가 0일 때 상수 b값이 존재하는데 위 그래프와 아래 그래프의 값의 차로 에러를 구하면 상수 b에 따라 에러값이 달라지는것 아닌가용! => 네 맞습니다. 상수 b를 반영하느냐, 아니냐 따라 error 값이 달라 집니다. 하지만 error 값이 달라지 더라도, 어차피 learning rate 값을 곱해 주기 때문에 bias가 적용된 error 냐, 아니냐는 아무런 의미가 없어 집니다. 

Q7. 처음에 Learning rate를 정할때는 임의로 정해야하나요? => Q2와 동일한 답변 참고 

09/02(수) 11시 빅데이터 도메인 Matrix factorization #1 Q&A

Q1. gradient 함수에서 weight_delta와 bias_delta의 leaning rate가 다른건가요? 그리고 왜 마이너스 값이 붙어있는건가요.? A. 달라질수 있습니다. 꼭 같은 값을 쓰라는 규칙은 정해져 있지 않습니다. => 보여 드린 코드에서 error = y - prediction(..),  된 부분을 반대로 error = prediction(..) - y로 수정하면 마이너스가 붙지 않아도 되겠네요.

Q2. lr의 적절한 값은 어떻게 알수있나요? A. 적절한 값은 처음에 알기가 어렵습니다. 라이브러리 에러값이 어떤 것이 나오냐에 따라 러닝레이트도 변동이 될 수 있을 것 같습니다.