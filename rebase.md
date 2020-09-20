# rebase

rebase를 사용하는 이유는 커밋을 이미 했는데 추가 작업이 생겨서 커밋 합치고 싶을 때
사용한다. 추가로 작업 후 다시 커밋하면 동일한 이름의 커밋 혹은 의미없는 새로운 커밋이 생기게 된다. rebase를 사용함으로서 추가 변경사항은 적용하면서 이전 커밋과 합칠 수 있다. 

`git rebase -i HEAD~N `

다음 명령어를 현재 커밋으로부터 N개 커밋에 대해 합치기,제거,수정이 가능하다. 
잔말말고 예시를 보자.

![rebasepng](https://user-images.githubusercontent.com/43857226/93711924-04efb400-fb8d-11ea-8cf6-9c006882dcf7.PNG)

**rebase test** 라는 메시지 작성해 위 내용까지만 마크다운 파일을 커밋하였다.
그 후 다음과 같이 **rebase test** 커밋로그가 있다. 이후 작성한 내용을 합칠 것이다.
작업 후 또 커밋하였다. 다음과 같이 로그 메세지가 뜬다.

![rebase2png](https://user-images.githubusercontent.com/43857226/93711925-05884a80-fb8d-11ea-984c-30ae9b1261a3.PNG)

두개를 합쳐보자!!!

`git rebase -i HEAD~2`

다음을 입력 이렇게 vi창이 뜰것이다.  *(vi창은 오랜만이군....잘쓰면 상당한 간지를 뽐낸다.)*

![gitrebase3png](https://user-images.githubusercontent.com/43857226/93711928-06b97780-fb8d-11ea-9d6f-da8c403aa1c1.PNG)


~~이거 또 수정하느라  하나의 커밋을 더 하였다.~~
이 vi창에서  각각 N개의 커밋에 대해 간략한 커밋 해시값과 커밋 메세지를 보여준다.
pick, squash등의 명령을 앞에 pick자리에 원하는 명령을 입력할 수 있다. 약어를 사용한다.

`pick  73a7725 rebase test`</br>
`s f852d3d rebase 2test`</br>
`s ce33e81 rebase 3test`</br>

입력하므로서 커밋을 합칠 수 있다.  **:wq** 로 저장하고 종료를 누르고 또 하나의 vi창이 뜨는데 
별건 아니고 커밋 메시지를 vi창에서 주석처리하거나 수정하여 원하는 메시지를 보여준다.

### fixup 

단순히 현재 커밋을 이전커밋으로 합치고 싶은거라면 (2개라면???) fixup을 이용하자

`pick <커밋해시값> <커밋메시지>`</br>
`f <커밋해시값> <커밋메시지>`</br>

이 명령어를 입력해준다면 특별한 작업없이 바로 커밋이 합쳐진다. 변경사항이 적용되면
하나의 커밋만이 남는다.

**주의** 
f <커밋해시값> <커밋메시지>
pick <커밋해시값> <커밋메시지>

이렇게 fixup이랑 pick순서를 바꿔버리면 rebase가 제대로 이루어지지 않는다.

`git rebase --abort`

입력 후 다시 진행해주자 순서를 꼭 바꾸지 말자..