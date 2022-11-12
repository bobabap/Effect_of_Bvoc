
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
