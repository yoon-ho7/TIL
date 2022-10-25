#### position : 아래의 목록에서 하나의 값을 선택해 요소 배치 방법 지정

---

#### 일반적인 문서 흐름에 따라 배치

- **static** - top, right, bottom, left 영향 X, **기본값**
- **relative** - **자기 자신**을 기준으로 **top, right, bottom, left** 값에 따라 
  오프셋을 적용

- **sticky** : 가장 가까운, 스크롤 되는 조상과 표 관련 요소를 포함한 컨테이닝 블록을 기준으로 **top, right, bottom, left** 값에 따라 오프셋 적용
  (**다른 요소에는 영향 X**)

---

#### 일반적인 문서 흐름에서 제거, 페이지 레이아웃에 공간 배정 X

**최종 위치는 top, right, bottom, left 값이 지정**

- **absolute** : 가장 가까운 위치 지정 조상 요소에 대해 상대적으로 배치
  (조상 중 위치 지정 요소가 없다면 body를 기준으로 삼음)
- **fixed** : 뷰포트의 초기 컨테이닝 블록을 기준으로 배치
  - 조상 중 하나가 **transform**, **perspective**, **filter** 속성 중 하나라도 
    **none**이 아니면 그 조상을 컨테이닝 블록으로 삼음

---

**위치 지정 요소 - position**이 **relative, absolute, fixed, sticky** 중 하나인 요소**상대 위치 지정 요소 - position**이 **relative**인 요소 (원래 위치에서 거리 지정)
**절대 위치 지정 요소 - position**이 **absolute** 또는 **fixed**인 요소 (모서리로부터 
거리 지정)
**끈끈한 위치 지정 요소 - position**이 **sticky**인 요소 (평소엔 상대 위치 지정 요소로 처리하지만 컨테이닝 블록이 자신의 플로우 루트에서 지정한 임계값을 넘으면 fixed처럼 화면에 고정, 컨테이닝 블록 반대편 모서리를 만나면 해제)

---

---

#### Flex : 레이아웃 배치 전용 기능으로 고안됨

**컨테이너에 적용하는 속성들**

- **display : flex;**
  - 가로로 배치
  - 자신이 가진 내용물의 width 만큼만 차지
  - height는 컨테이너의 높이만큼 늘어남 (컬럼 레이아웃을 만들 때 편리)

- **flex-direction**
  - **row (기본값)** : 가로 배치
  - **row-reverse** : 역순 가로 배치
  - **column** : 세로 배치
  - **column-reverse** : 역순 세로 배치
- **flex-wrap**
  - **nowrap (기본값)** : 줄바꿈 X , 넘치면 삐져나감
  - **wrap** : 줄바꿈
  - **wrap-reverse** : 역순으로 줄바꿈
- **flex-flow** : **flex** - **direction**/**wrap**을 한 번에 지정 가능

---

#### justify-content : 메인축 방향 정렬

##### justify : 가로 방향 정렬

- **flex-start (기본값)** : 시작점으로 정렬 (가로-왼쪽,세로-위쪽)
- **flex-end** : 끝점으로 정렬 (가로-오른쪽,세로-아래)
- **center** : 가운데 정렬
- **space-between** : 아이템 '사이'에 균일한 간격
- **space-around** : 아이템 '둘레'에 균일한 간격
- **space-evenly** : 아이템들의 사이와 양 끝에 균일한 간격 (IE,엣지 지원 안함)

---

#### align-items : 수직축 방향 정렬

##### align : 세로 방향 정렬

- **stretch (기본값)** : 수직축 방향으로 끝까지 늘어남
- **flex-start** : 시작점으로 정렬 (가로-위,세로-왼쪽)
- **flex-end** : 끝으로 정렬 (가로-아래,세로-오른쪽)
- **center** : 가운데 정렬
- **baseline** : 텍스트 베이스라인 기준 정렬

---

#### align-content : 여러 행 정렬

**flex-wrap: wrap;**  <= 설정된 상태(무조건 두 줄 이상으로 나옴))

- **stretch** : 각 행이 끝까지 늘어남

- **flex-start** : 왼쪽 위로 정렬
- **flex-end** : 왼쪽 아래로 정렬
- **center** : 가운데 정렬
- **space-between** : 위쪽과 아래쪽으로 각각 정렬
- **space-around** : 각 행마다 위 아래로 균일한 간격
- **space-evenly** : 각 행 사이와 양 끝 모두 균일한 간격

---

---

### flex : 아래의 세 개 속성을 한 번에 쓸 수 있음

**생략해서 쓰는 속성은 0이 됨**

---

#### flex-basis : Flex item 기본 크기 설정(row-너비,column-높이)

- **flex-basis** : 기존보다 크다면 늘어나고 원래 넘으면 그대로 유지
- **width** : 원래 넘는 것도 크기가 맞춰짐

#### flex-grow : flex-basis의 값보다 커질 수 있는지를 결정

- **0보다 큰 값**이 세팅되면 유연한 박스로 변하고 **원래 크기보다 커지며 빈공간을 메움**

- **flex-basis를 제외한 여백 부분**을 **flex-grow에 지정된 숫자 비율**로 나누어 가짐

#### flex-shrink : flex-basis의 값보다 작아질 수 있는지를 결정

- **0보다 큰 값**이 세팅되면 유연한 박스로 변하고 **flex-basis보다 작아짐**
- **0으로 세팅**하면 **고정 크기**를 **width로 설정**하여 **고정폭 유지 가능 **(기본값 1)

---

#### align-self : 수직축으로 item 정렬

- **해당 아이템 수직축 방향 정렬**

---

#### order : 배치 순서

- **각 아이템들의 시각적 나열 순서를 결정하는 속성**

- **z-index로 Z축 정렬** (숫자가 클수록 위로)

