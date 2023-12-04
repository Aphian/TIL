### Open API 크롤링 (ex. naver)
- 로그인 방식 오픈 API
- 비로그인 방식 오픈 API
- `client_id` 와 `client_key`를 발급 받아 사용
- 한글 처리 `import urllib.parse`
- url 형식 파싱 : `from urllib.parse import urlparse`
- `urllib.parse.quote('문자열')` : 문자열을 통신 코드로 변경
- 요청객체 생성 :  `request = urllib.request.Request(url)`
- 헤더 추가 
```
request.add_header("X-Naver-Client-Id",client_id)
request.add_header("X-Naver-Client-Secret",client_secret)

```  
- 응답 확인 : `response = urllib.request.urlopen(request)`
- 파라미터 : `param = '?query=' + keyword +'&display='+str(disnum)` 넣어주면서 크롤링
- 이용 가이드에 나와 있는 변수에 따라 설정이 가능함
  1. `lastBulidDate` : 검색 시간
  2. `total` : 전체 검색 결과
  3. `start` : 몇번째 검색 부터 반환 했는지
  4. `display` : 추출 개수 `default = 10`

#### 공공데이터 API 크롤링
- `data.go.kr` 사이트 공공데이터
- ex.
```
import requests

url = 'http://apis.data.go.kr/B552657/ErmctInsttInfoInqireService/getParmacyListInfoInqire'
params ={'serviceKey' : s_key, 'Q0' : '서울특별시', 'Q1' : '강남구', 'QT' : '1', 'QN' : '삼성약국', 'ORD' : 'NAME', 'pageNo' : '1', 'numOfRows' : '10' }

response = requests.get(url, params=params)
print(response.content)
```
