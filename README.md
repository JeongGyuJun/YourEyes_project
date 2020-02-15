# YourEyes_project
- 본 소스는 서버 코드 관련하여 제공. - !문제가 될 경우 내리겠습니다.

## 시각장애인을 위한 보행사고 예방 및 재난문자 알림이 

![image](https://user-images.githubusercontent.com/45933225/74583778-f1380a00-500d-11ea-8afc-c180fcd5129e.png)
- 과제 유형 : PBL(Problem-Based-Learning 약칭 PBL)
- 과제 기간 : 2019.01.11. ~ 2019.01.31
- 과제 목표
1. 발생한 위험 상황을 직접 볼 수 없는 시각장애인을 위하여 시각장	애인이 어플리케이션 음성인식을 통해 구동 시 어플리케이션 내 기능	인 카메라를 통해 촬영된 상황을 마이크로소프트 Azure Cloud를 사용	하여 분석하고 분석된 상황을 음성으로 어플리케이션 사용자인 시각	장애인에게 제공하는 것을 목표로 함.
2. 재난 상황 및 기상 정보에 따른 재난예비정보, 특보, 상황전파 등의 	정보 수신 시 신속한 확인이 어려운 시각장애인을 위하여 시각장애인	이 어플리케이션을 사용할 시 현재 발령되어 있는 재난예비경보, 기	상특보, 상황전파 등을 자신이 위치한 지역에 맞게 수신하고 음성으	로 제공하여 시각장애인의 재난 피해 예방을 목표로 함.
3. 국내 외 여러 요건으로 발생하는 미세먼지 주의, 경보 횟수가 점차 	늘어남에 따라 당일 미세먼지 경보를 손쉽게 알 수 있도록 미세먼지 	발령 현황을 공공기관 데이터 포털에서 제공하는 API를 사용하여 저	장 후 사용자의 위치에 따라 음성으로 제공하는 것을 목표로 함.

### 개발 환경 및 사용 API/TOOL
![image](https://user-images.githubusercontent.com/45933225/74583753-aae2ab00-500d-11ea-8c81-8c26bc63ad36.png)


- 아래 항목 순서
1. 서버/클라이언트
2. 사용 언어 및 개발 환경
3. 세부 수행 내역
4. 이미지 분석을 통한 상황 알림이

![image](https://user-images.githubusercontent.com/45933225/74583780-fd23cc00-500d-11ea-8511-d48e63bddde3.png)
![image](https://user-images.githubusercontent.com/45933225/74583782-00b75300-500e-11ea-949d-3fb7947a78b2.png)

#### 서버 
▷ 사용 언어: 파이썬 
▷ 개발 환경: Microsoft Azure Claude Computer
▷ 사용 Open API: 재난예비특보조회 서비스(공공데이터포털 Open API)
사용자의 어플리케이션에서 현재 위치를 전송 시 해당위치에 해당되는 재난 특보를 조회하여 전송클라이언트
▷ 사용 Open API: 대기오염정보 조회 서비스(공공데이터포털 Open API) 사용자의 어플리케이션에서 데이터 요청 시 금일 미세먼지 상태를 조회하여 전송
서버
▷ 사용 Open API: Azure Storage(저장소), Computer Vision API(이미지 분석), Naver Papago NMT번역(인공신경망 기반 기계번역), 어플리케이션(클라이언트)으로 수신된 사진파일을 분석한 영어 텍스트를 한글 텍스트로 번역하여 재전송

#### 클라이언트
(어플리케이션)
▷ 사용 언어: 자바
▷ 개발 환경: Android Studio
▷ 사용Open API: Google Speech API(TTS)
▷ HttpURLConnection(통신)데이터(NULL) 값을 서버로 전송, 서버로부터 수신한 미세먼지 상태 텍스트를 음성으로 제공
▷ 사용Open API: Google Geocoder(GPS, NET), Google Speech API(TTS)
▷ HttpURLConnection(통신)현재 위치를 서버로 전송, 서버로부터 수신한 재난 예비 특보 텍스트를 음성으로 제공, 미세먼지 기상 현황 음성 제공
▷ 사용 Open API: Google Speech API(TTS), Google Speech API(STT), Retrofit2 Library, 시각장애인의 음성을 인식하여 촬영된 사진을 서버로 전송, 서버에서 가공된 한글 텍스트를 수신하여 음성으로 제공, 재난문자 음성 제공 


