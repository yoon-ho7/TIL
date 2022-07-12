## DOM 조작하기

### 요소 찾기

---

- **document.getElementById("아이디")** : `요소 ID`로 요소 찾기
- **document.getElementByTagName("태그 이름")** : `태그 이름`으로 요소 찾기
- **document.getElementByClassName("클래스 이름")** : `클래스 이름`으로 요소 찾기
- **document.querySelectorAll("선택자")** : `CSS 선택자` <u>전부</u> 찾기
- **document.querySelector("선택자")** : `CSS 선택자 중` <u>첫 번째 하나</u>만 찾기

---

### 요소 조회

---

- **textContent** - 선택한 요소에서 `HTML 요소`를 **제거**한 <u>순수한 텍스트 데이터의 값</u>
- **innerHTML** - 선택한 요소의 `HTML 태그`를 그대로 제공하여 <u>보안에 취약</u>
  - **사용자로부터 전달받은 콘텐츠를 추가할 때**는 <u>사용하지 않는 것</u>이 좋음![image-20220712131344426](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220712131344426.png)

---

### 요소 수정

---

**선택한 요소를 수정할 때** - 새로운 값을 <u>조회한 그대로 할당</u>하면 됨
![image-20220712131155450](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220712131155450.png)

---

### 요소 생성 및 추가

---

- **createElement**를 사용하여 `새로운 요소`를 만듦
  ![image-20220712131534557](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220712131534557.png)

이렇게 만들어진 요소는 <u>메모리에만 존재</u>(`메소드`를 **생성**하여 <u>DOM에 추가</u>해야 함)
![image-20220712131635459](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220712131635459.png)

- **createTextNode**를 사용하여 `텍스트 노드`를 추가 가능
  ![image-20220712131939903](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220712131939903.png)

---

### 요소 삭제

---

![image-20220712132026374](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220712132026374.png)

---

### 요소 교체

---

- **Node.replaceChild()** : <u>특정 부모 노드의 한 자식 노드</u>를 <u>다른 노드로 교체</u>하는 메소드
  ![image-20220712132201524](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220712132201524.png)