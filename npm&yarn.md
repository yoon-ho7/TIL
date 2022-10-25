### npm

---

**Node.js의 기본 패키지 관리자**

- **명령어**
  - **npm init** : package.json 생성
  - **npm install** : package.json 파일 및 해당 종속성에 나열된 모든 모듈을 설치
  - **npm install package_name@버전** : 특정 패키지의 특정 버전 설치
  - **npm install 주소** : 특정 저장소 내 패키지 설치. 주로 github을 이와 같이 설치
  - **npm install package_name -g** : 옵션. 글로벌로 설치. 로컬의 다른 프로젝트도 이 패키지를 사용 가능
  - **npm uninstall** : 패키지 삭제 명령어
  - **npm update** : 설치한 패키지들을 업데이트
  - **npm dedupe** : 중복 설치된 패키지들을 정리해주는 명령어

- **package.json** : 프로젝트 정보와 의존성을 관리하는 문서
  - 어떤 패키지(오픈소스)를 사용하는지, 어떤 버전을 사용하는지 등을 기록

---

### yarn

---

**페이스북에서 만든 JS 패키지 매니저**

**npm**의 단점을 보완하기 위해 만들어짐

- **명령어**
  - **yarn init** : package.json 생성
  - **yarn or yarn install** : package.json 파일 및 해당 종속성에 나열된 모든 모듈을 설치
  - **yarn add package_name@버전** : 특정 패키지의 특정 버전 설치
  - **yarn add 주소** : 특정 저장소 내 패키지 설치. 주로 github을 이와 같이 설치
  - **yarn global add package_name** : 옵션. 글로벌로 설치. 로컬의 다른 프로젝트도 이 패키지를 사용 가능
  - **yarn remove** : 패키지 삭제 명령어
  - **yarn upgrade** : 설치한 패키지들을 업데이트
  - **npm dedupe** : 중복 설치된 패키지들을 정리해주는 명령어



- **속도**(performance)
  - **패키지를 설치할 때 병렬로 처리하기 때문에 performance와 speed가 증가**
  - 다운받은 패키지 데이터를 **캐시**에 **저장**
  - **중복된 데이터**는 다운로드하지 않음
  - `npm`에 비해 패키지 **설치속도**가 매우 **빠름**
- **안정성**(stability) / **보안성**(security)
  - **yarn.lock**이나 **package.json**으로부터 설치만 함
  - **yarn.lock**은 **모든 디바이스**에 **같은 패키지**를 **설치**하는 것을 보장
    - 버전 차이로 인해 생기는 버그 방지