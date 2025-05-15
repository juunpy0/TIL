# Branch 전략
Branch 전략은 여러 개발자가 동시에 작업할 수 있도록 협업을 효율화하고, 상용 서버에 안정적인 코드를 배포할 수 있도록 돕는 Git 사용 방식이다.

## Branch 기본 구조

**서버 위치에 따른 분류** 

서버 위치는 *로컬 서버(Local server)* 와 *원격 서버(remote server)* 두 가지의 분류로 나뉜다. *로컬 서버(Loval server)* 는 사용자의 로컬 환경, 즉 자신의 컴퓨터 내에서 구동되는 서버이고 *원격 서버(remote server)* 는 네트워크를 통한 물리적 또는 가상 서버이다. 사용자의 로컬 환경과 분리된 위치에 존재하는 게 특징이다. 

카카오톡을 살펴보면 카카오톡의 로컬 서버(Local server)는 사용자의 휴대폰이나 컴퓨터에서 앱이 실행되는 곳이고 원격 서버(remote server)는 사용자끼리의 보낸 메세지를 저장하고 전달하고 관리하는 곳이다. 

### Git의 기본 동작
#### 로컬 저장소 & 원격 저장소

> init

로컬 저장소(Local repository)와 원격 저장소(Remote repository)는 앞서 설명한 로컬 저장소(Local server), 원격 서버와 (remote server)와 대응된다. 사용자가 자신의 컴퓨터(로컬 서버)에서 작성한 코드가 위치한 파일을 로컬 디렉토리(Local directory)라고 하고 이 디렉토리를 Git으로 관리하고 Github로 보내기 위해서 로컬 저장소로 `git init` 명령어를 통해 초기화 해줘야 한다.

####  add & Commit & Push

로컬 저장소에 있는 디렉토리를 원격 저장소로 보내는 작업을 **Push** 라고 한다. Push(발행)하기 위해선 add(추가) → Commit 과정이 필요하다. 

&nbsp;


> git add .

**add**는 현재 작업 중이던 파일을 원격 저장소로 보내기 위한 Staging area(무대)에 올리는 작업이다. 

&nbsp;

> git commit -m "commit massage"

**Commit**은 Staging area(무대)에 올린 파일을 Push하기 위해 대기 상태 즉 하나의 버전으로 저장하는 작업이다.

> git push origin main
커밋된 버전을 원격 저장소 main 브랜치로 Push(발행)하는 작업이다. 





 







