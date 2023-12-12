### Next.js
- 풀스택 웹 애플리케이션 구축을 위한 `React` 프레임 워크
- 서버 사이트 렌더링, 정적 사이트 생성, `API` 개발에 대한 쉬운 솔루션을 제공하는데 중점

#### 개발자들의 선택 이유
- 성능 : 자동 코드 분할, 서버 사이드 렌더링, 정적 사이트 생성과 같은 내장된 성능 최적화 기능을 제공하여 개발자가 죄소한의 노력으로 빠르고 반응성 있는 웹 애플리케이션을 만둘 수 있다.
- 개발자 경험 : 핫 모듈 교체, 자동 페이지 라우팅, 통합된 `API` 개발과 같은 기능을 제공하여 보도 쉽게 구축하고 반복적인 작업을 수행할 수 있도록 지원
- 유연성 : 어떤 데이터 소스와도 함께 사용할 수 있으며, 기존 프로젝트에 쉽게 통합훌 수 있어 다양한 웹 개발 요구에 유연이 대응
- 생태계 : 크고 활발한 개발자 커뮤니티

#### 설계 철학
- 간결함 : 시작을 위한 최소한의 구성과 애플리케이션 개발을 안내하는 명확한 규칙 세트를 제공하여 개발자들에게 간단하고 직관적인 개발경험 제공
- 성능 : 성능에 중점을 두며, 자동 코드 분할, 서버 사이드 렌더링, 정적 사이트 생성과 같은 내장된 최적화 기능을 제공하여 빠르고 반응성이 뛰어나도록 해준다.
- 확장성 : 쉽게 확장할 수 있또록 설계 되어 있음.

#### SSR(서버 사이드 렌더링)
- 웹 애플리케이션에서 페이지를 서버 측에서 생성하고 렌더링하는 기술
- `SSR`을 사용하면 각 요청에 대해 서버에서 `HTML` 페이지를 생성하여 초기 렌더링에 필요한 모든 데이터와 마크업을 포함할 수 있습니다. 
- 애플리케이션의 인지 성능을 향상시키고 검색 엔진이 콘텐츠를 쉽게 크롤링하고 인덱싱할 수 있음
- `SSR`은 웹 애플리케이션의 초기 로딩 속도, `SEO`, 사용자 경험 등을 개선하기 위해 사용되며, `CSR`과 함께 사용하여 최적의 사용자 환경을 제공하는 데 중요한 역할
- 하는 이유
    1. `SEO(Search Engine Optimization)` 개선 : `SSR`을 사용하면 초기 `HTML`에 콘텐츠가 포함되어 검색 엔진 최적화를 개선
    2. 퍼포먼스 개선 :  `SSR`은 서버에서 페이지를 완전히 렌더링하여 클라이언트로 보내기 때문에 초기 로딩 속도가 개선되고 사용자가 더 빠르게 콘텐츠를 볼 수 있음.
    3. 사용자 경험 향상 : `SSR`은 초기 로딩 시간을 단축하여 사용자 경험을 향상

#### SSG(정적 사이트 생성)
- `SSG`를 사용하면 `HTML` 페이지가 빌드 시간에 생성되고 정적 에셋으로 제공되어 각 요청마다 서버 사이드 렌더링이 필요하지 않게 됩니다
- `SSG`는 콘텐츠가 많은 웹사이트나 업데이트 빈도가 낮은 애플리케이션에 적합하며, 빠른 로딩 시간과 효율적인 캐싱을 가능

#### Next.js 주요 기능 / 장점
- 자동 코드 분할 : `Next.js`는 각 페이지에서 사용되는 컴포넌트를 기반으로 애플리케이션 코드를 자동으로 작은 번들로 분할하여 사용자가 현재 페이지에 필요한 코드만 다운로드하도록 합니다. -> 로딩 시간 단축 및 성능 향상
- 핫 모듈 교체 : `Next.js`는 핫 모듈 교체`(HMR)`를 지원하여 개발자들이 전체 페이지를 새로 고치지 않고도 애플리케이션의 변경 사항을 볼 수 있습니다. -> 개발 경험 향상 / 개발 프로세스 가속화
- 자동 페이지 라우팅2 : `Next.js`는 `pages` 디렉토리의 파일 구조를 기반으로 자동으로 페이지 라우팅을 처리합니다. -> 개발 프로세스 간소화 / 수동으로의 라우트 구성 불필요
- 통합된 API 개발 : `Next.js`는 개발자들이 애플리케이션 내에서 쉽게 서버리스 API 경로를 생성할 수 있도록 지원하여 풀 스택 애플리케이션 개발 프로세스를 간소화하고 프론트엔드와 백엔드 간의 원활한 통신을 가능하게 합니다.
- 하이브리드 렌더링 : `Next.js`는 서버 사이드 렌더링(`SSR`)과 정적 사이트 생성(`SSG`)을 모두 지원하여 개발자들이 특정 사용 사례에 가장 적합한 방식을 선택하거나 하나의 애플리케이션 내에서 두 기술을 결합할 수 있습니다.
- 내장된 `CSS` 및 `JavaScript` 지원 : `Next.js`에는 `CSS` 모듈 및 `styled-components`와 같은 인기 있는 `CSS-in-JS` 솔루션에 대한 내장 지원이 포함되어 있습니다. 현대적인 `JavaScript` 기능 지원
- 확장성 : `Next.js`는 플러그인, 미들웨어, 사용자 정의 설정을 통해 쉽게 확장할 수 있도록 설계되었습니다. -> 개발자들은 프레임워크를 특정 요구에 맞게 맞춤화 / 다른 도구와 서비스 통합 가능