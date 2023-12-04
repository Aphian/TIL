### telegram_API

- telegram API 뿐만 아니라 보통의 오픈 API 를 사용 할 때 개발자에게 TOKEN 을 부여하여 구별함
- telegram API
  - `getUpdates` : telegramBOT 에서 사용자(Client)가 보낸 메시지를 telegram 에서 확인 (약간 수동의 느낌이 듬)
  - `setWebhook` : 봇에 대한 업데이트가 있을 때 마다 JSON 직렬화된 업데이트가 포함된 HTTPS_POST 요청을 URL로 보냄(자동의 느낌)
  - `sendMessage` : 사용자(Client)가 보낸 메시지에 따라 telegram 이 정해진 답변을 보냄


## 모듈 
### requests
- HTTP 요소에 요청을 하기 위해 필요한 모듈
- `import requests` 실행 하면 가져와진다.
  - ex) URL = `https:// ~~~~~ ` -> requests.get(URL) 

### beautifulSoup
- HTML과 XML 문서들의 구문을 분석하기 위한 파이썬 패키지
- HTTP 요소(HTML)에 요청으로 인해 가져와지는 데이터는 개발자가 활용할 수 있도록 얻어짐
- `requests`로 가져온 데이터를 추출하기 위해 HTML에 있는 내용들을 분석하는 프로세스

### dotenv
- 보통으 API에 사용을 위해 부여되는 TOKEN 등 노출이 되면 안되는 중요도가 높은 소스코드를 분리할 때 사용되는 모듈
- `.env` 파일 안에 만듬
