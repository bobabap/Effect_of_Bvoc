파일 데이터명
산림청 국립산림과학원_청정넷

2021년7월 지점별 측정데이터 (10분 단위)

국립산림과학원에서 운영하는 청량 아시아 산림 미세먼지 측정넷(AICAN)은 산림 및 도시숲 내에 설치되어 산림의 미세먼지 농도를 실시간으로 측정 및 분석하여 10분 단위로 국민들에게 정보를 제공하는 데이터입니다. (2021년 기준 상반기, 하반기)

국립환경과학원의 최종확정자료

2021년 7월 지역별 측정데이터 (1시간 단위)
참고 https://www.konetic.or.kr/include/EUN_download.asp?str=DBSV_GREEN_REPORT&str2=2225

https://www.dongascience.com/news.php?idx=27212 미세먼지가 오존에 미치는 영향

## 1) 데이터 선정 이유 및 문제 정의 # ✅
해당 데이터를 선정한 이유는 수목에서 방출되는 BVOC(생물 유래 휘발성 유기화합물)은 수목 스스로 스트레스에 대하여 방어하기 위한 역할을 합니다.

이러한 BVOC 물질 중 일부는 수목의 번식 및 생장을 조절하는 것뿐 아니라 인간의 건강 증진에 기여하는 것으로 알려져 있습니다.

-휘발성 유기화합물(VOC)은 대류권 오존 및 2차 에어로졸의 형성을 위한 중요한 전구체입니다.
하지만 건강 위험과 환경 오염을 방지하기 위해서는 대기오염 물질의 전구체를 줄여야 합니다.
VOC의 상당 부분은 중부 유럽과 같이 인구가 밀집된 지역 생물(BVOC)에서 기원합니다.
대한민국 전체를 봐도 상당히 밀집지역이기 때문에 해당할 것 같습니다.


## 2) 데이터를 이용한 가설 및 평가지표, 베이스라인 선택 # ✅
## 3) 글로벌 변화에 따른 예상 BVOC 배출량 BVOC 배출량에 대한 미래 기후 및 토지 사용 변화의 영향과 이들의 대기 화학 및 기후에 대한 피드백 반응을 평가하기 위한 모델이 필요하다. 이를 위해 아직 개발된 접근법은 거의 없다. 동적인 식생 모델과 결합할 때, 단위 잎 면적당 배출에 대한 직접적인 영향뿐만 아니라 식생 특성의 변화와 관련된 간접적 영향도 고려해야 한다는 것이 명백해진다. 따라서 종의 풍족도 및 식생 분포에 영향을 미치는 관리 결정은 BVOC 배출에 큰 영향을 미칠 것으로 예상한다. https://www.konetic.or.kr/include/EUN_download.asp?str=DBSV_GREEN_REPORT&str2=2225

위의 논문 내용을 보면 토지 사용변화나 식생 특성의 변화와 관련이 있을 수 있다고 합니다.

저는 토지사용관련 데이터는 찾아보지 않아서 위에 두 데이터로만 분석하겠습니다.

선형회귀모델를 사용할 것이고 평가지표는 MSE, RMSE, MAE, R2_score를 사용할 것입니다.

randomforestregressor 도 사용할 수 있는지 확인 해보겠습니다.

BVOC = 생물 유래 휘발성 유기화합물\ AVOC = 인공 유래 휘발성 유기화합물

산림 미세먼지 측정넷(AICAN)\ 산림 및 도시숲 내에 설치되어 산림의 미세먼지 농도를 실시간으로 측정

BVOC(생물 유래 휘발성 유기화합물)측정은 산림\ AVOC(인공 유래 휘발성 유기화합물)측정은 도시숲 내에서 측정한 것으로 보임
