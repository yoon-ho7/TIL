## Git

### 활용

- Version 관리
- 
  Backup 기능
- Collaboration 기능

---

### 제공하는 기능의 기본 개념

- Status
- Branch & Merge & conflict
- Remote Repository

---

#### 버전 관리하기

- **Status 개념**
  - Working Tree - Staging Area - Repository
  - git init을 통해 깃을 사용하기 시작하면 Status 개념이 해당 디렉토리에 적용됨
  - [Working Tree] : 현재 작업 중이거나 수정이 발생한 파일, 사항을 의미(작업 영역)
  - [Staging Area] : git add를 통해 버전관리 대상이 된 파일, 디렉토리 등을 의미
  - [Repository] : 버전관리 된 대상(저장소)

- **CLI 버전관리**
  - 새롭게 발생하는 수정 사항들을 각각의 버전으로 내역 관리할 수 있음
  - 이전 버전으로 되돌리거나 브랜치를 활용하여 병합 후 새로운 버전으로 만드는 등 작업을 풍부화 할 수 있음

1) 디렉토리에 git 삽입하여 git 사용 시작
   - 디렉토리 내부에 .git 이라는 숨김 폴더가 생성됨

> git init

2. Status 상태 확인 후 버전관리 대상으로 만들기 = tracking하기

   - untracked 상태를 tracking 상태로 전환하여 버전관리 대상으로 만듦(최초)

   - tracking 중인 상태의 파일을 수정한 후 add 하여 수정한 사항을 커밋을 하기 위한 버전관리 대상으로 올림

> git status
>
> git add 파일명,확장자명
>
> git add . (디렉토리 내부 전체)

3. Status 상태 확인하고, 커밋하기
   - changes to commit

> git commit -m "message..."
>
> git commit -am "message.." : 트래킹 중인 대상을 한번에 add하고 commit
>
> git commit --amend :커밋 메시지 수정

3)  ''
   - 커밋 메시지 수정 시 사용할 에디터 설정 변경(vim 또는 nano 등)

> git config --global core.editor "vim"

4. commit log 확인하기
   - 커밋 키값 또는 해시 아이디 확인

> git log
>
> git log -p : revert 확인
>
> git log --all --graph --oneline : branch관계도 확인

5. revert, reset : 커밋 되돌리기와 커밋 삭제하기
   - [커밋1]-[커밋2]-[커밋3]-[커밋4]
   - revert : 커밋 되돌리기, 커밋내역 유지(반드시 커밋마다 순차적으로 revert. 수정사항의 되돌리기이기 때문에 충돌방지)

> git revert 커밋4 = 커밋4의 수정사항을 되돌려 커밋3이 되도록 함

5.  ''
   - reset: 커밋 삭제

> -git reset --hard 커밋3 (커밋3버전이 되도록 한다는 의미)

6. diff

   - git의 차이점 확인

   > -git diff

---

## Branch

#### 개념

- Base 개념의 공통의 부모를 중심으로 동일한 작업과 새로운 작업을 구분하여 버전관리를 할 수 있도록 하는 개념

```
                              	[Main Work_1]					
                                       |				 	
				[Main Work_2].....base!				
		|			|			|		
	[child A Work_1] 	[Main Work_3]    	[child B Work_1]	
					|			/		
				      [        Merge Work_1       ]		
```

-HEAD의 개념 : HEAD는 git이 현재 가리키고 있는 브랜치 및 브랜치의 버전을 의미
Checkout은 HEAD를 제어, revert나 reset은 HEAD가 아니라 브랜치 자체를 제어하여 버전 상태를 관리

---

#### 버전관리하고 Merge하기

1. 브랜치 생성하기

> git branch New브랜치명

2. 브랜치로 현재 상태를 이동하고 작업하기

> git checkout New브랜치명
>
> git add . + git commit -m "message..."

3. Merge 하기

> git checkout main
>
> git merge 다른브랜치명

4. Conflict 3way merge

| A    | Base | B    | 3way Merge | 변경                           |
| ---- | ---- | ---- | ---------- | ------------------------------ |
| C    | C    | C    | C          | 변경없음                       |
| CA   | C    | C    | CA         | A만 변경되어 A의 변경사항 반영 |
| C    | C    | CB   | CB         | B만 변경되어 B의 변경사항 반영 |
| CA   | C    | CB   | Conflict   | A와 B 모두 변경되어 충돌       |

- git은 Conflict 사항을 알려줌

  : >>>>>>HEAD(A)

  수정내용 CA

  ============

  수정내용 CB
  <<<<<<<브랜치명(B)

---

### Git으로 Backup하고 Collaboration, 협업하기

#### Repository

- Local Repository와 Remote Repository
- 지역저장소와 원격저장소 개념
- git hosting service를 이용하여 원격저장소에 작업 내역을 백업하고 버전관리하며 협업할 수 있다
- git hosting service : github, gitlab(private 무료), bigbuket

#### Backup 하기

1. git hosting service 사용, remote repository 생성 후, http 주소 확인
2. remote 지역저장소와 원격저장소 연결하기

> 1. git init
>
> 2. git remote add origin [https://...주소](https://...xn--9l4b19k/)
>
> 3. git remote -v :연결된 원격저장소의 주소 확인

**3)** git push 하여 작업 내용을 원격저장소에 저장

> git add .
>
> git commit -m ".."
>
> git push // 또는 git push origin 브랜치명
>
> git push --set -upstream origin main

**4)** git pull 하여 origin의 수정된 내용을 지역 저장소에 반영한 후 작업 (협업 시)

> git pull

**5)** git clone 하여 기 작업된 origin의 내용을 지역 저장소에 복제한 후 협업하기

> git clone [https://..주소](https://..xn--9l4b19k/)

**6)** git clone 시 유의 사항

- noe-modules와 같은 환경파일은 업로드 하지 않는다 (gitignore 내부에 폴더명 작성)
- git clone하여 협업 시 npm install하여 환경을 셋팅하고 작업할 수 있다 (package.json은 clone되므로 가능)
- 기타, node, firebase 등등 환경 맞춰주기