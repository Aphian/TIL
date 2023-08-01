### selenium 패키지 모듈 동적 크롤링
- `selenium` : `webdriver` 라는 `API`를 통해 운영체제에 설치된 웹 브라우저를 제어하는 함수 포함한 패키지
- 설치 필요 : `pip install selenium`
```
# api 서비스 연결객체(chrome webdriver 서비스 객체)
service = Service()
# 크롬 브라우저 옵션 정보를 os에서 추출
options = webdriver.ChromeOptions()

# 드라이버 객체 생성
driver = webdriver.Chrome(service=service, options=options)

# 페이지접근
url = 'https://map.naver.com'
driver.get(url)
```
- `html 소스 활용 bs4 파싱`
```
html = driver.page_source
soup = BeautifulSoup(html, 'html.parser')
```
- 자동입력 방지 문자 우회
- `javascript` 코드를 활용
    - `selenium`이 `javascript` 코드를 실행하게 코드 작성
    - `driver.execute_script(코드) 함수` : 자바스크립트코드 실행