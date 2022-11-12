[목적]

- 넷플릭스, 왓챠 등등 많은 영화 추천 서비스 플랫폼들이 있습니다
어떤 추천 방식이 사용자의 만족을 이끌어 낼 수 있을까 고민하여 만들게 되었습니다.

[목표] 

'user_number', 'sword', 'movie_id', 'score', 'movie_title', 'genres’

특성들을

```python
def pearsonR(s1, s2):
    s1_c = s1 - s1.mean()
    s2_c = s2 - s2.mean()
    return np.sum(s1_c * s2_c) / np.sqrt(np.sum(s1_c ** 2) * np.sum(s2_c ** 2))
```

피어슨 상관계수를 이용해 
특정 영화를 본 유저의 추천이라는 제목으로 영화를 추천해준다.

[단계]

1. 네이버에서 영화 정보 크롤링
- user_number
- movie_title
- movie_number
- movie_score
- user_name

[결과]

웹사이트 구현은 완성하지 못했지만 좋아하는 영화를 입력했을 때

영화와 그 영화의 장르를 보여준다.

input = 타이타닉

output = ![image](https://user-images.githubusercontent.com/87513112/201477667-e6181d0a-104c-49cd-8885-46db697c0a33.png)



### [BVOC(생물 유래 휘발성 유기화합물)이 오존에 미치는 영향](https://github.com/bobabap/Effect_of_Bvoc)

2022.03.18 ~ 2022.03.22

[목표]

산림청 국립산림과학원_청정넷에 미세먼지 데이터를 가지고 BVOC가 오존에 미치는 영향을 알아본다.

[단계]

1. BVOC를 제외한 나머지 특성들은 삭제하고 오존데이터를 날짜에 맞춰서 합쳐준다.
2. BVOC데이터의 미세먼지는 ozone데이터에 있는 값으로 사용
3. 측정 장소 지역으로 묶어서 처리
    
    ![Untitled](https://user-images.githubusercontent.com/87513112/201477680-0dfcbe9b-7cbc-4170-9fa1-7500499638e2.png)

 

4. LinearRegression을 사용해 연관성 확인

```python
# Create linear regression object
regr = LinearRegression(n_jobs=-1, normalize=True)

# Imputation
my_imputer = SimpleImputer()
x_train_imputed = my_imputer.fit_transform(x_train)
x_test_imputed = my_imputer.fit_transform(x_test)

# Train the model using the training sets
regr.fit(x_train_imputed, y_train)

# Make predictions using the testing set
y_pred = regr.predict(x_test)

# The mean squared error
print("MSE: %.8f" % mean_squared_error(y_test, y_pred))
      
# Explained variance score: 1 is perfect prediction
print('R2 score:', r2_score(y_test, y_pred))

from sklearn import metrics
print("MAE:", metrics.mean_absolute_error(y_test, y_pred))
print('RMSE:', np.sqrt(metrics.mean_squared_error(y_test, y_pred)))
```

1. 이상치 제거

[결과]

<img width="392" alt="다운로드 (4)" src="https://user-images.githubusercontent.com/87513112/201477685-9823a3b9-bd76-45a9-85ee-0382cdfa44db.png">


R2 score 가 0.8 이상 나왔지만 검증을 제대로 하지 않아 정확한 값이라고 볼 수 없다.
