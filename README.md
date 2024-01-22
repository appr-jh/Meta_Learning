
---

# Few shot Learning

Few shot learning은 10개 미만의 한정된 샘플로부터 학습할 수 있는 머신러닝 방법론을 의미합니다.

--> Meta Learning, Transfer Learning

---

# Meta Learning

meta learning complete

<img src="https://github.com/appr-jh/Meta_Learning/assets/100187238/08a0288e-3710-4ac9-9d81-5132b85a3a40" width="200" height="100">

<img src="https://github.com/appr-jh/Meta_Learning/assets/100187238/3f011817-d10e-4b67-8816-1470a6bbac65" width="600" height="200">


weight (0~5)

--> 0~3 -> lstm c0, h0, bias(c0, h0)

--> 4~5 -> fc, bias(fc)

---

### Fewshot dataset -> 작은 dataset 크기 기준

---

1개 MAP --> (T: 100)

현재 batch_size (10974) -> epochs 60 (Train 60, Test 20)

---

2개 MAP --> (T: 200) 

현재 batch_size (10974) -> epochs 60 ~ 170 (Train 170, Test 30)

Train set --> random


---

Few-Shot Dataset (Batch size: 5, 10)

---
## Result

Fewshot Learning -> apply the meta-learning

loss
![image](https://github.com/appr-jh/Meta_Learning/assets/100187238/9671be1f-a80c-4a1c-b408-aaba29773bbd)

---

1. average loss (100개의 few shot task를 평균내서 나오는 loss)

K = 10 (few shot data: 10)

<img src="https://github.com/appr-jh/Meta_Learning/assets/100187238/ce7e7960-5e77-413e-ab63-8d340b6e57eb" width="400" height="300">

K = 20 

<img src="https://github.com/appr-jh/Meta_Learning/assets/100187238/5d659fa5-125e-4f99-bac6-331f9d925d56" width="400" height="300">


---

2. initial point (적용해서 pretrained 보다 더 낮은 loss를 보여줌)

Meta learning test (K = 10)

<img src="https://github.com/appr-jh/Meta_Learning/assets/100187238/1587ad55-f430-4979-96ad-d236cda20dfd" width="800" height="700">


<br>
<br>

Meta learning test (K = 20)

<img src="https://github.com/appr-jh/Meta_Learning/assets/100187238/3cf9b1d0-4452-4022-b454-0d5e7f99f28a" width="800" height="700">

---

# Performance

task 별 data 크기가 다름 -> sequence data 특징을 batch size로 자를 수 없으니 (padding or elimination)

dataset -> shuffle (x) -> 섞이면 안 됨

train set과 test set이 independent (random으로 task를 선택)

Test를 두 가지로 생각가능 ==> (random initial point) / tradeoff

= Test (Few shot (10 ~ 20) / Task (xxxx ~ 10974))

<br>
<br>

이론적으로 Meta Learning 시킨 것이 Fewshot Learning 할 때 

- result 1 (dataset: fewshot)

  비교군 (No Meta-learning)보다 더 빠른 시간내에 학습의 정확도는 높고 loss는 작은 결과를 도출할 수 있음

  (성능이 많이 떨어질 것으로 예상) -> dataset이 작기 때문에

- result 2 (dataset: fewshot)

  random initial point를 조정해서 loss 줄이는 것을 확인

- result 3 (dataset: batchsize)

  trade off 경계 생각 
    -> 적은 dataset으로 정확도를 ~ 이 정도 손해보면서 사용가능하다.

  정확도는 confusion matrix에서 (TP + TN) sample 개수로 생각

- result 4 (dataset: batchsize)

  속도 차이가 많이 날지는 모르겠는데 loss를 빨리 떨어지는 것을 비교 

  (MAML 적용 시킨 것을 비교) -> TASK (10974) -> 여러 testset을 적용시켜서 평균 시간을 구하는게 나을듯

