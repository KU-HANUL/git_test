## Git 입문
* [git - 간편 안내서](http://rogerdudler.github.io/git-guide/index.ko.html)
* [git 정식 설명서](http://git-scm.com/book/ko)

## Git 이란
* 아래 설명들은 위 설명서를 봐도 모르겠거나 보기 귀찮은 사람을 위해서 준비했다.
* Git은 버젼 관리, Github 같은 저장소를 이용한 백업, 공동 프로젝트 관리 등을
* 해주는 프로그램이다.

## Git 시작하기
* 지금과 같이 이미 존재하는 Git 저장소를 복사해오는 경우를 다루겠다.
* Git 저장소를 복사해온다 : 
```
$ git clone [git-저장소-주소]
```
* 이때 git-저장소-주소는 https와 ssh 둘중에 고를 수 있는데 **ssh를 이용하는
* 것이 정신건강에 좋다.**
* ssh를 선택했다면 [ssh-key
* 설정](https://help.github.com/articles/generating-ssh-keys)을 해야 한다.
* 링크를 따라가서 설정해보자. 여기서 phase phrase는 일종의 비밀번호라고
* 생각하면 된다. (https 주소를 사용하기로 마음먹었다면 화이팅!)
* ssh-key 설정을 마쳤다면 다음과 같이 Git 저장소를 복사해온다 : 
```
$ git clone git@github.com:KUNPL/LAMPS_Standalone.git
```

## Git 관리하기
* git을 처음 사용한다면 자신을 나타내는 이름과 메일 주소를 설정해주자.  
```
$ git config user.name "나의 이름"
$ git config user.email "나의 메일 주소"
```
* ```git config --list``` 라고 치면 자신의 정보를 볼 수 있다.
* ```git status``` 라고 치면 현재 Git 관리상태를 볼 수 있다.
* 항상 작업을 시작하기 전에 최신 버젼으로 업데이트를 하는게 좋다.  
```
$ git pull
```
* 수정된 파일이나 새로 추가하고 싶은 파일이 있다면 다음과 같이 쓴다  
```
$ git add [파일이름1] [파일이름2]
$ git add [파일이름3]
...
```
* 커밋(Commit)을 한다 (작업을 저장한다고 생각하자)  
```
$ git commit
```
* 커밋을 하면 vi가 열리면서 무엇이 변경되었는지 기록 할 수 있다. 메세지를 다
* 쓰고나면 vi를 저장하고 닫자. vi 창이 따로 열리는게 싫다면 다음과 같이 써도
* 된다.
```
$ git commit -m '하고 싶은 말'
```
* 마지막으로 내가 한 커밋을 남들이 볼 수 있도록 저장소에 올리기 위해서 다음과
* 같은 명령어를 쓴다  
```
$ git push origin master
```
* 에러가 뜨면서 push가 되지 않는 경우 수많은 경우가 있는데
  1. 명령어를 잘못쓴 경우
  1. https 주소를 사용한다면 가장많이 하는 실수는 url에 아이디를 쓰지 않은 경우
  1. ssh 주소를 사용하는데 ssh-key를 등록하지 않은 경우
  1. 저장소 관리자가 권한을 주지 않은 경우 
  1. 커밋할 내용이 없는 경우
  1. 최신 버젼으로 업데이트가 되지 않은 경우, ```git pull```을 먼저 해보자. (확실하지 않다)
