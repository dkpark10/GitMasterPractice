# Git 을 마스터하자 

### 이론

커밋: 파일 추가하거나 변경내용 자신 컴퓨터 로컬에 저장 
푸쉬: 커밋한걸 원격저장소에 업로드 하는 작업
브랜치: 분기임 트리처럼

전체 과정은 이렇다.
1. git init or git clone
2. 코드 작성 및 편집
3. 생성,변경,삭제를 git 인덱스에 추가 **(git add)**
4. 내 로컬피씨에 커밋    **(git commit)**
5. 원격저장소에 업로드 **(git push)**

1번은 초기 2~4번만 반복한다.
먼저 커밋을 하고 완벽할 때 푸쉬하는것이 일반적이다.

### 커밋,푸쉬 과정

폴더 생성하고 다음 명령어 입력하자

`git init
`

그럼 폴더에 깃 숨김폴더가 생성될 것이다.
그런다음 변경된 내용을 폴더에 추가해주자.
커밋할 준비를 하기 위한 임시로 저장할 위치이다.

`git add <파일>
`
이제 커밋을 해보자

`git commit -m "commit message"
`

커밋메시지는 잘 기록해야 한다. 그래야 로그 따라 추적하기 쉽다...
그 다음에 잘 기록되어있는지 확인한다. 무엇이 추가되었고 무엇이 편집되었는지

`git status
`

푸쉬를 하기전에 원격저장소의 정보를 추가해야한다. 

`git remote add gitpractice https://github.com/dkpark10/GitMasterPractice
`

깃주소와 레포지토리 이름을 입력해주자 쉽다.
remote 뒤 gitpractice 은 리포지터리 이름은 구분하기 쉽게 별명을 지어준 것이다. 
그 다음은 이제 원격저장소에 푸쉬해줘야 된다.

`git push gitpractice master 
`

아까 별명지은 gitpractice 레포에 master 브랜치로 푸쉬한다는 뜻이다. ^^
