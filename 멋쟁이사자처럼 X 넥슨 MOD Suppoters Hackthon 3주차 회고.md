<div class = title align = center>

# 3주차

<br></br>

</div>

<div align = center>
 
# Resources
</div>
 
## 스크립트의 이해
- 

## 네트워크의 이해
-  

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
