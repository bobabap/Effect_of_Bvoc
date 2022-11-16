
### [BVOC(생물 유래 휘발성 유기화합물)이 오존에 미치는 영향](https://github.com/bobabap/Effect_of_Bvoc)

2022.03.18 ~ 2022.03.22


[목표]

산림청 국립산림과학원 청정넷에 미세먼지 데이터를 가지고 BVOC가 오존에 미치는 영향을 알아본다.

[진행]

1. BVOC를 제외한 나머지 특성들은 삭제하고 오존데이터를 날짜에 맞춰서 합쳐준다.
2. BVOC데이터의 미세먼지는 ozone데이터에 있는 값으로 사용
3. 측정 장소 지역으로 묶어서 처리
    
    ![Untitled](https://user-images.githubusercontent.com/87513112/201477680-0dfcbe9b-7cbc-4170-9fa1-7500499638e2.png)
    
4. LinearRegression을 사용해 연관성 확인
5. IQR 방식을 이용한 이상치 데이터(Outlier) 제거
6. 다중공선성이 가장 높은 feature를 삭제
r2 score = 0.82 —> r2 score= 0.78

[결과]

<img width="392" alt="다운로드 (4)" src="https://user-images.githubusercontent.com/87513112/201477685-9823a3b9-bd76-45a9-85ee-0382cdfa44db.png">

R2 score = 0.78 
BVOC가 오존에 어느정도 영향이 있는 것으로 판단
