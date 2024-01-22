# MetaLearning

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

Fewshot Learning -> apply the metalearning

loss
![image](https://github.com/appr-jh/Meta_Learning/assets/100187238/9671be1f-a80c-4a1c-b408-aaba29773bbd)

---

average loss (100개의 few shot task를 평균내서 나오는 loss)

K = 10 (few shot data: 10)

<img src="https://github.com/appr-jh/Meta_Learning/assets/100187238/ce7e7960-5e77-413e-ab63-8d340b6e57eb" width="400" height="300">

K = 20 

<img src="https://github.com/appr-jh/Meta_Learning/assets/100187238/5d659fa5-125e-4f99-bac6-331f9d925d56" width="400" height="300">


---

Meta learning test (K = 10)

<img src="https://github.com/appr-jh/Meta_Learning/assets/100187238/1587ad55-f430-4979-96ad-d236cda20dfd" width="800" height="700">


<br>
<br>

Meta learning test (K = 20)

<img src="https://github.com/appr-jh/Meta_Learning/assets/100187238/3cf9b1d0-4452-4022-b454-0d5e7f99f28a" width="800" height="700">

---


