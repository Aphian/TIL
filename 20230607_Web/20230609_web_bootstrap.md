## Design
- 작은 컴포넌트 -> 큰 컴포넌트 순으로 작업
- 모바일 -> 데스크탑 순

## Bootstrap
- 웹사이트의 디자인을 보다 편하게 도와주는 CSS, JS 프레임 워크
- 하나의 코드로 반응형(기기의 크기에 따라서 화면이 반응하는것)으로 작동하게 만들수 있음.
- `<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-9ndCyUaIbzAi2FUVXJi0CjmCapSmO7SnpJef0486qhLnuZ2cdeRhO02iuK6FUUVM" crossorigin="anonymous">`
- `<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js" integrity="sha384-geWF76RCwLtnZ8qwWowPQNguL3RmwHVBC9FhGdlKrxdiJJigb/j/68SIy3Te4Bkz" crossorigin="anonymous"></script>`
- 이용하여 외부에서 가져옴.

### BreakPoint
- bootstrap에서 장치 또는 viewport 크기에 따라 반응형 레이아웃으로 작동하는 방식을 결정하는 사용자 정의 너비
- 6개의 포인트가 있음
- ex(default) = 0, s=576px, md=768px, lg=992px, xl=1200px, xxl=1400px

### container
- view 내에서 contents 등 패딩 및 정렬에 도움을 주는 기본 빌딩 블럭
- grid 시스템을 사용할 때 필요함.

### grid system
- 12개의 열 시스템, 6개의 기본 응답 계층
- 모든 모양과 크기의 레이아웃을 구축 가능

### Gutters
- grid 에서 반응적으로 콘텐츠를 배치하고 정렬하는데 사용되는 열 사이의 패딩을 조절