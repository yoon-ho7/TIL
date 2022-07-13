## Fetch API / Ajax

### Fetch API

---

- **JS 기본 라이브러리**
- **Promise 기반**으로 구성되어 있어 **비동기 처리 프로그래밍 방식**에 잘 맞는 형태
- `then`이나 `catch`와 같은 체이닝으로 작성 가능

---

### Ajax

---

- `XMLHttpRequest` 객체를 이용해서 <u>웹 서버와 비동기로 통신</u>하고, DOM을 이용해서 웹 페이지를 <u>동적으로 바꿔주는</u> 프로그래밍 기법
- **Asynchronouse JavaScript XML**
- `XML`을 사용하는 건 드물고 `JSON`을 사용
- 페이지 새로고침 없이 **특정 데이터만 리로드**
- 서버로부터 데이터를 받고 작업을 수행

---

### Ajax 구현하기

---

- 대표적인 3가지
  1. XMLHttpRequest
  2. **Fetch API**
  3. JQuery

---

### Fetch API의 기본 형태

---

- **Promise 기반**이기 때문에 <u>체이닝 형태</u>로 사용될 수 있음
- `then`과 `catch`로 체이닝 한 형태
  <img src="C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220713130913335.png" alt="image-20220713130913335" style="zoom:67%;" />

---

### header 조작하기

---

- Fetch API에서도 header를 조작 가능(=> option 객체에 headers에 들어갈 내용들을 지정하는 방법)
  <img src="C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220713131048344.png" alt="image-20220713131048344" style="zoom:67%;" />

---

### Fetch API GET Method

---

**Fetch API**로 **HTTP**의 `GET` 메서드를 사용하여 데이터를 서버로 보내는 방법
<img src="C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220713131354954.png" alt="image-20220713131354954" style="zoom: 67%;" />

---

### Fetch API POST Method

---

**Fetch API**로 **HTTP**의 `POST` 메서드를 사용하여 데이터를 서버로 보내는 방법
<img src="C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220713131723001.png" alt="image-20220713131723001" style="zoom:67%;" />

---

### Fetch API PUT Method

---

**Fetch API**로 **HTTP**의 `PUT` 메서드를 사용하여 데이터를 서버로 보내는 방법
<img src="C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220713131919438.png" alt="image-20220713131919438" style="zoom:67%;" />

---

### Fetch API PUT Method

---

**Fetch API**로 **HTTP**의 `DELETE` 메서드를 사용하여 데이터를 서버로 보내는 방법
<img src="C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220713132707093.png" alt="image-20220713132707093" style="zoom:67%;" />