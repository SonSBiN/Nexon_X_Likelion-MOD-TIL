<div class = title align = center>

# 3주차

<br></br>

</div>

<div align = center>
 
# Resources
</div>
 
### 스크립트의 이해
- 대부분의 Lua 문법을 다룬다. (Lua 문법 + 추가된 형태)
- Workspace->MyDesk에서 원하는 스크립트를 제작 후 사용한다.
- 반복문 사용
<ol>
*1부터 10까지 log 찍는 행위를 반복
for count = 1, 10, 1 do 
<ol>
    log(count)
</ol>
end
</ol>

- 조건 분기문
<ol>

if 조건 then
<ol>

행동 
</ol>
end
</ol>

- Logic
<ol>

+ Logic은 World상에 딱 하나만 존재하기때문에, Log 함수를 실행할 때 로그가 나온다. 하지만 Component에서 출력하는 Log는 해당 Component를 쓰는 Entity가 있어야 한다.
</ol>

- Component
<ol>

+ Component는 Log를 출력하는 함수가 있을경우, 해당 Component를 가지고 있는 Entity수에 따라 출력된다.
</ol>

- function: 어떠한 기능들을 모아놓은 것.
<ol>

+ C언어의 함수와 다를바가 없다.
+ 기본적은 함수가 있다.
+ 주로 사용하는 함수는 OnBeginPlay, OnUpdate, OnEndPlay
+ 컴포넌트가 초기화될때 OnBeginPlay, 끝날때 OnEndPlay, 주기적으로 사용하는게 OnUpdate
+ 자기자신을 호출시엔 self. 사용
+ 자신의 Component 내의 함수 호출시엔 self:함수 사용
+ Component가 달려있는 Entity 접근방법:  
self.Entity.~~
+ 자신의 위치의 좌표를 받아오는 방법:  
local myEntityPosition = self.Entity.Transformcomponent.Position
+ 위치를 조작하는 방법 (1초에 1번씩 x좌표를 0.5증가)
<ol>  
for count=1, 5, 1 do  
<ol>

myEntityPosition.x = myEntityPosition.x + 0.5
wait(1)
</ol>
end

</ol>
</ol>

### 네트워크의 이해

- 동기화
<ol>

- MOD에선 기본적으로 1개의 Server와 다수의 Client가 있다.
- Entity를 생성시, Server에도 존재하고 Client에도 존재한다. (각각 하나씩 추가가 되는 개념)
- Server, 혹은 Client에서 값을 바꾸는데, 두개가 동시에 변하지 않는다면, 문제가 된다. 따라서 각각 바꾸게되면 서로의 값을 맞추는 작업을 한다.  
->이게 동기화
- MOD에서 Property는 동기화 옵션을 해준다.
- 변수 위에 [Sync] 라고 되어있으면 동기화, 클릭시 [None] 으로 바뀌는데 그러면 동기화X
- any, table 등, 동기화, 비동기화를 바꿀수 없는것도 존재.
- Server는 1개지만 Client는 여러개가 가능하다.
- Server에서 값을 바뀌면, Client의 값은 다 같이 바뀐다. (Server는 1개라서 권한을 가진다.)
- 반대의 상황에서는 안된다. => 동기화의 방향은 항상 단방향 (Server -> Client)
- OnSyncProperty라는 함수는, Client 기준으로만 작성을해서, 여기서 조작시에는 해당 Client에서만 적용이 된다.
</ol>

- Function의 공간, 실행제어
<ol>

+ 해당 함수가, Server와 Client 모두에서 실행 가능한데, 이것을 Server만 실행을 하는 함수인지, Client만 실행을 하게 하는 함수인지 정하는것.
+ 5가지: Server, Client, ServerOnly, Client Only, multicast
+ ServerOnly, ClientOnly: 각각 서버와 ,클라이언트에서만 실행할 수 있게 하는것.
+ Server, Client: 이 함수가 Server 혹은 Client에서 돌아가야한다.  
client는 func가 server에서 불리면, 자동으로 client쪽으로 패킷을 보내서 통신을 해서 client가 호출이 되게한다.  
server는 이 함수가 client에서 불렸다 하더라도, server에 보내서 실행하라.  
Multicast: client에도 보내고, server에도 보내는 것.
+ Timming이 있는데, server에서는 server순서대로 코드를 읽어나가는데, client에서 요청을 보내는 시간안에, server에서 다른것을 실행하면, 더 늦게 올 수 있다.  
1. log("begin play")
2. server() 
3. client()
4. log("end play")
+ 실행시
1. begin play
2. server()
3. end play
4. client
+ 순서대로 찍힌다. 따라서 타이밍 이슈가 있으므로, 언제 넘어가서 언제 넘어오는지 등 잘 고려해서 코딩해야함.
+ Client 내에서만 생성하고싶은 Entity가 있음 ex) UI, HP, 입력 등
+ 위와 같은것들은 "나"를 위한 것들이므로, Client에서만 관리를 한다.
+ Effect는 경우에 따라서, 서버에서 제어를 한다.  
근데, 특정 이펙트를 한 Client에서만 보이게 하고싶을때는 Local Entity를 사용한다.
+ 최적화할때, Client 쪽 logic를 사용한다.
+ 어쨋든 입력과 UI관련은 Client에서 제어를 한다.
</ol>

<br></br>
<br></br>

<div align = center>
 
# Docs
 
 </div>

## ch06

### 스크립트 에디터 오리엔테이션
- MOD는 스크립트 에디터를 사용하여 크리에이터가 원하는 컴포넌트나 로직을 만들 수 있습니다.
- 스크립트의 문법은 Lua Script를 사용하여 다양한 MOD API를 지원합니다.
- 스크립트 컴포넌트 추가  
![Sciprt Component 추가](images/Script%20Component%20%EC%B6%94%EA%B0%80.png)
- OnBeginPlay 함수
<ol>

+ 이 함수는 스크립트 컴포넌트가 실행될 때 처음에 한 번 불리는 함수이다.
</ol>

- log 함수
<ol>

+ log 함수는 스크립트 작성 시 가장 기본적이면서도 가장 자주 사용되는 함수 중 하나 입니다.
파라미터로 넘겨진 값을 메이커 하단 콘솔 창에 출력해줍니다.
변수나 프로퍼티 값, 또는 함수의 리턴 값들을 콘솔창에 출력하여 확인할 수 있습니다.
</ol>

- 작성한 Script Component 추가
<ol>

+ 스크립트 컴포넌트를 완성했더라도 실제 컴포넌트가 삽입된 엔티티가 없으면 스크립트가 실행되지 않습니다.
따라서 추가한 HelloMapleWorld 컴포넌트를 맵에 배치한 엔티티 중 하나에 넣어야 합니다.
</ol>

### 스크립트 디버그
- 중단점
<ol>

+ 스크립트 디버깅의 시작은 중단점 설정에서 시작됩니다. 이상이 발생하거나, 오작동의 원인으로 의심되는 코드 라인에 중단점을 설정 또는 해제하는 방법을 알아봅니다.
+ 중단점은 원하는 코드 라인에 F9를 눌러 설정할 수 있습니다.
</ol>

- 중단점 (Breakpoint)
<ol>

+ 중단점을 여러 라인, 여러 스크립트에 설정하다 보면 내가 어디에 중단점을 설정했는지, 불필요한 중단점이 아직 남아있는지 확인이 어려울 때가 있습니다. 이때 Breakpoints 창을 통해 설정된 모든 중단점의 확인이 가능합니다.
+ BreakPoint 창 오픈  
![Breakpoint 창 오픈](images/Breakpoint%20%EC%B0%BD%20%EC%98%A4%ED%94%88.png)
+ Breakpoint Entry, Method, Line  
![Breakpoint Entry, Method, Line](images/Breakpoint%20%EC%B0%BD%20Entry%2C%20Method%2C%20Line.png)
+ 중단점 이동, 삭제  
![Breakpoint 이동, 삭제](images/Breakpoint%20%EC%9D%B4%EB%8F%99%2C%20%EC%82%AD%EC%A0%9C.png)
</ol>

- 디버그
<ol>

+ 디버그 시작  
![디버그 시작](images/%EB%94%94%EB%B2%84%EA%B7%B8%20%EC%8B%9C%EC%9E%91.png)
+ 코드 파악  
![코드 파악](images/%EC%BD%94%EB%93%9C%20%ED%8C%8C%EC%95%85.png)
+ 디버깅 중지  
![디버깅 중지](images/%EB%94%94%EB%B2%84%EA%B9%85%20%EC%A4%91%EC%A7%80.png)
+ 디버깅 중 코드 실행  
![디버깅 중 코드 실행](images/%EB%94%94%EB%B2%84%EA%B9%85%20%EC%A4%91%20%EC%BD%94%EB%93%9C%20%EC%8B%A4%ED%96%89.png)
</ol>

- Watch Expression
<ol>

+ 마우스 오버를 이용해 변수나 프로퍼티의 값을 확인하는 방법은 간편하게 값을 하나씩 확인하기엔 편리하지만, 코드가 한 줄씩 실행될 때마다 특정 변숫값이 어떻게 변하는지 알고 싶을 때는 계속 마우스를 올려 확인해야 하므로 상당히 불편합니다.  
Watcher Watch Expression은 프로퍼티/함수 내부나 선언된 변수를 Watch Expression에 등록해 코드가 실행될 때마다 값이 어떻게 변경되는지 추적할 수 있어 매우 편리합니다.
+ Watch Expression 창 오픈
![Watch Expression 창 오픈](images/Watch%20Expression%20%EC%B0%BD%20%EC%98%A4%ED%94%88.png)
+ 디버깅 중 값을 알고자 하는 변수나 프로퍼티 명을 Add Expression에 작성합니다.
+ Watch Expression에 변수나 프로퍼티가 등록되면, 코드를 한 줄씩 실행하며 다음과 같이 값의 변화를 추적할 수 있습니다.  
![Watch Expression 변수 확인](images/Watch%20Expression%20%EB%B3%80%EC%88%98%20%ED%99%95%EC%9D%B8.png)
</ol>

-  Call Stack
<ol>

+ 콜스택은 현재 디버깅 중인 함수가 어디서부터 호출되었는지를 확인하는 데 사용됩니다.
+ Call Stack 창 오픈  
![Call Stack 창 오픈](images/Call%20Stack%20%EC%B0%BD%20%EC%98%A4%ED%94%88.png)
+ 다음과 같이 OnBeginPlay를 시작으로 Method1, Method2를 거쳐 Method3을 호출하는 스크립트에서 Method3 내부를 디버깅 중이라 했을 때, Call Stack을 이용해 Method3까지 호출된 순서와 실행 공간을 확인할 수 있습니다.
![Call Stack 예시](images/Call%20Stack%20%EC%98%88%EC%8B%9C.png)
</ol>

### 함수
- 컴포넌트는 기본적으로 프로퍼티와 함수로 구성된다. 그중 함수는 객체지향 프로그래밍에서 사용되는 용어로, 특정 액션을 수행하기 위한 코드들의 집합체라 할 수 있습니다.
- MOD의 함수는 함수의 호출 주체가 누구냐에 따라 기본 이벤트 함수와 사용자 지정 함수로 나눌 수 있습니다.
- 기본 이벤트 함수: 게임 시작, 플레이 중, 게임 종료 시 등 특정 이벤트가 발생했을 때 호출되는 함수로, 호출 시점과 함수 이름이 정해져 있으며 모든 동작의 진입점이 되는 함수입니다.
- 사용자 지정 함수:  호출 시점이 정해져 있지 않고, 액션의 목적에 따라 이름을 자유롭게 지을 수 있습니다.  
![함수 소개](images/%ED%95%A8%EC%88%98%20%EC%86%8C%EA%B0%9C.png)
- 함수의 선언과 삭제
- 함수 리턴 타입 설정
- 함수 정의
- 파라미터
- 함수 호출
### MOD 기본 이벤트 함수
-
### 엔티티와 컴포넌트 참조
-

<br></br>

## ch07

### 서버와 클라이언트
-
### 실행 제어
-
### 프로퍼티 동기화
-
