# Github Git 하기

### 첫 사용자인 경우

#### 1. 로컬 PC에 작업 폴더 생성해서 저장소 생성
#### 2. 깃허브에 원격 저장소(repository) 만듬
#### 3. 로컬 저장소 (원도우 :cmd, 맥 OS) 선언하기
    
    //로컬 저장소 생성
    $ git init

    
#### 4. 로컬 저장소 ↔ 지정한 원격 저장소 연결
    - 깃허브 저장소에서 초록색 "Code"버튼을 누르면 보이는 HTTPS 탭에 적힌 주소를 사용

#### 5. 연결되었는지 확인
    
    //연결된 원격 저장소 확인
    $ git remote -v

    
5-1. 연결한 것 삭제
    

    //기존 원격 저장소와의 연결 삭제
    $ git remote rm origin

    
#### 6. 위까지 지정하고 나서 파일 업로드 준비
- 깃허브 저장소 기본 branch 이름은 main이다.
    - 새로 깃허브 생성시 main으로 되어 있지만, 예전 생성시 master인 가능성이 높아 수정해야 한다.
- 로컬 저장소에 있는 README.md을 원격 저장소에 가지고 오기 (동기화)
    
    ```
    //(README.md가 있다면) 원격 저장소의 파일 가져오기
    $ git pull origin [브랜치 이름]
    ```
    
- main branch에서 가져올 것이기 때문에 git pull origin main 이라고 치면 된다.
이걸 하고나면 내 컴퓨터에도 원격 저장소에 있던 README.md 파일이 생긴 것을 볼 수 있다.
항상 파일을 올리기 전에는 pull을 해줘야 이후 작업이 정상적으로 처리된다.

#### 7. 파일 올리기
  - 총 3단계로 이루어지는데, add → commit → push 순서
    
>   7-1. **add**
    
 
    //모든 변경사항을 올리는 경우
    $ git add .
    
    //특정한 파일만 올리는 경우
    $ git add [파일/디렉토리]

    
	- add 후 로컬 저장소에 변경된 파일 확인
    

    //현재 버전 상태 확인
    $ git status

    
    - 빨간색 → untracked files, 추가 되지 않았다는 걸 의미
    - 초록색으로 뜨는 경우 추가 되었다는 의미
	- add 했는데 취소하고 싶을 경우
    

    //add한 파일 모두 취소
    $ git rm --cached -r .
    
    //특정 파일만 add 취소
    $ git rm --cached [파일]

    
    
>   7-2. **Commit**
    
    
    

    //커밋 메시지 없이 커밋하기
    $ git commit
    
    //커밋 메시지를 적는 경우
    $ git commit -m "commit message"

    
    - 왠만하면 메세지를 작성하고 commit 하는 것 추천
    
    
>   7-3. **Push**
    

    //로컬 저장소에서 원격 저장소로 올리기
    $ git push origin [브랜치 이름]
    --main 브랜치에 올릴 것이라서 git push origin main

    
8. 깃허브 저장소에 가서 파일 업로드 확인    

### 저장소 있는 경우

- 지정된 저장소 경로 진입 후 아래와 같이 입력

```markdown
$ git pull origin main
$ git add .
$ git commit -m "commit message"
$ git push origin main
```


### 예외
- 추가로 옵션 및 에러 상황 발생해서 검색 했을때 참고 [https://blog.naver.com/yaki80/222135060431](https://blog.naver.com/yaki80/222135060431)
- 첫 push 진행 시 깃허브 아이디,비밀번호를 넣으라고 요청하는데, 비밀번호는 지정 저장소에 깃허브 토큰 생성 후 연결 동기화해야 원활하게 업로드 진행이 가능해진다. (최대 지원 기간 90일)
