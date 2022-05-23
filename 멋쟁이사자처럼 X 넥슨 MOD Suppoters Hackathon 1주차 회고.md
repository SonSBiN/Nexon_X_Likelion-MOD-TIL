<div class = title align = center>


# 1주차

</div>
<div align = center>
 
# Resources
</div>
 
## 기본의 이해
- 상단 메뉴
<ol> <!--들여쓰기-->

### --- File ---
+ Publish: 만든 MOD 를 다른 사용자들이 이용 가능하게 한다.  
+ Revision: 각 버전을 저장하고, 이전 시점으로 되돌아갈 수 있다. 특정버전 다운로드 가능  
+ Setting: 그래픽, 사운드, 등등 설정 가능
### --- Panels ---
+ 원하는 패널들을 화면에 도킹 가능  
### --- Window ---
+ 도킹 불가능한 패널들.  
+ Map List : 새로운 맵들을 추가, 삭제 가능하다.  
+ MapleStory Map: 원작의 다양한 맵을 불러올 수 있다.  
+ Scrip Manager: 스크립트 Sample 들을 다운받아서 추가 가능하다.

</ol>

- Tile
<ol>

+ 화면 우측 상단   
+ 그리드 정보: 발판의 섬세한 위치 확인 가능.  
+ 발판 정보: 발판의 모양에 따라서 지나갈 수 있는지 없는지 확인  
+ 여기서 시작: 시작위치 조정 가능  
+ 모바일 시뮬레이터: 모바일 버전의 가상 버튼까지도 화면 가능  
+ 성능 통계: 현재 이 게임의 FPS, 메모리, 마우스커서 좌표 확인 가능  
</ol>
 
 - Object
<ol>

+ 기본적인 이미지의 기능은 있지만, 부딪히거나 하는 설정은 없다.
</ol>

- Monster
<ol>

+ 실제 메이플에 존재하는 몬스터 (움직임까지) 구현되어있음. 몬스터 퇴치시 얻는 아이템, 경험치 등은 따로 구현이 필요하다.
</ol>

- NPC

<ol>

+ NPC들의 이름, 대화등을 따로 설정이 가능하다.
</ol>

- Foothold
<ol>

+ 발판기능을 가지고 있는 객체들  
+ 우클릭-Edit Foothold
</ol>

- BGM

<ol>

+ 해당 멥의 BGM 설정 가능
</ol>

- Background

<ol>

+ 배경이미지를 설정
</ol>

- 새 그룹 추가

<ol>

+ 새로운 카테고리를 만들고, 자신만의 카테고리로 이용할 수 있다.
</ol>

- 화면 우측 Scene Maker

<ol>

+ 내가 넣은 객체들 확인 가능.  
+ 각 객체들의 폴더안에 다른 객체를 넣으면, 함께 움직이거나 같은 설정까지 할 수 있다.  
+ 추가 삭제 이름바꾸기 등등 가능하다.
</ol>

- 화면 우측 Wordspace

<ol>

+ 객체를 추가하면 MyDesk 폴더 안에 생성이 되지만, 중복되는 객체 추가시에는 추가로 생성되지 않는다.  
+ 내 Scene에서 삭제해도, MyDesk에는 아직 더미파일이  남아있다.  
+ Script, 폴더 등등 추가로 가능하다.  
+ 일종의 파일 탐색기.  
+ 객체를 변형하여 그것을 다른 맵, 혹은 다른 게임에도 적용하고 싶다면, Scene Maker 에서 내가 변형한 객체를 우클릭-> make original model을 클릭하면, Workspace에 생성된다. +이것은 변형한 객체와 동일하게 된다.
</ol>

- Property

<ol>

+ 만약 아무런 속성이 없는 Object에 속성을 넣고싶다면, Property의 맨 밑에 있는 Add Component.  
ex) 속성이 없는 Object 에 움직임을 넣고 싶다면, TweenLineComponent 를 이용한다.  
+ 객체가 원래 가진 속성이아닌 다른 모든 속성들을 다 추가 가능하다.  
ex) 위의 Object에서 사다리가 가진 climbable Component 속성을 넣으면, 해당 Object도 탈 수 있게 된다.
</ol>

- Map Layer

<ol>

+ 타일 같은경우, 한 Layer에 다른 타일만 설치 가능하다.  
+ 따라서 Layer를 추가한다음에 다른 Layer에는 다른 타일도 사용이 가능하고, 마찬가지로 객체들도 추가가 가능하다.  

</ol>

- SpriteRendererComponent

<ol>

+ 객체들의 앞,뒤 관계를 바꾸고자 할때는 Property에 SpriteRendererComponent 속성에 가서 OrderInLayer 에서 바꿔준다.  
+ 숫자가 커질수록 더 앞에 배치된다.
</ol>

- 새로운 Script

<ol>

+ Workspace에서 MyDesk 우클릭 -> Create Scripts -> Create Component 하고, 더블클릭하면 나오는 곳에서, 각각의 Property를 추가하고, 객채에서 Add Component를 한다음에 해당 Component를 검색하여 추가하면, 객채에 Component 추가 가능하다.  
+ Function을 +로 클릭하면, 메소드 추가 가능하다.  
+ Entity Event Handler를 통해서 등록을하고, 알아보는것도 가능. 이후에 설명  
+ 해당 메소드를 Server 설정인지, Client 설정인지, 둘 다인지도 설정 가능하다. 
작성한 Script는, Workspace에서 우클릭 -> Export To를 사용하면, 파일로써 공유가 가능하다.  
+ 또한 Plain Text에서 내용을 복사하여, 다른사람이 그것을 Plain Text에 붙여넣는다면, 파일단위가 아닌 Text 단위로도 공유가 가능하다. 
</ol>

- Sprite Picker

<ol>

+ 객체가 가지고 있는 속성들을 그대로 두고, 이미지만 바꾸고 싶다면, Property -> SpriteRendererComponent-> SpriteRUID 를 클릭하면 Sprite Picker가 뜬다. 거기에 있는 다른 이미지로 교체가 가능하다.
+ 혹은 다른 객체를 불러와서 그것의 RUID값을 복사한뒤 붙여넣으면 바뀐다.
</ol>

## 기본 개념의 이해
- Entity, Component, Property, Service, Logic, Model 등
- Entity는 어떤 곳에 존재하는 객체, 그 객체가 어떤일을 하는지는 Componenet, 그 어떤일을 어떤식으로, 어떤 속성을 가지고 하느냐는 Property에 의해서 결정이 된다.  

- Entity: 맵을 구성하고있는 어떠한 '것'
<ol>

+ 몬스터, Object, NPC, 지형 등 월드를 구성하고있는 어떠한 것 (보이지 않는것도 존재 ex Scene 메이커에 존재하는 것들도 포함. 심지어 최상위에 있는 World)
+ 각각의 Entity는 여러개의 component로 이루어져있다.
+ Scene Maker에서 부모 엔티티와 자식 엔티티가 있는데, 자식 엔티티를 부모 엔티티 안에 넣으면, 부모 엔티티를 작업했을때 자식 엔티티들도 다 같이 변한다. (배경맵을 만들때 유용함)
</ol>

- Compoenent: 어떠한 기능단위를 그 기능에 특화되게 만들어놓은 형태. Entity에 속해있고 여러가지 Component가 존재한다.
<ol>

+  이것들을 추가함으로써 Entity가 그러한 기능들을 가지게 된다.
+ Workspace에 Base Environment -> NativeScripts -> MODComponent에 가면 기본적으로 제공되는 Component가 있다.
</ol>

- Property: 포탈 Component는 포탈의 기능을 부여하는것이고. 세부적인 것들 (어디로 이동할 것인지 등)을 지정하는 것이다. 고유 설정하게 하는것.

- Service, Logic, Model

- Component는 Entity에 속해있고 여러가지로 나타나 있지만, Service는 월드상에 딱 하나만 존재하는 어떠한 "것".
- Service와 Logic들은 게임 내에서 딱 하나만 존재한다.
- Service: MOD에서 Core한 부분에서, 실제로 유저가 제어하기 힘든 부분들을 제공하는 Logic들

<ol>

+ 수정이 불가능함.
</ol>

- Logic: 게임을 돌리기위해 사용되는 게임 Logic들

<ol>

+ 유저가 직접 작업이 가능함.
</ol>

- Model: 어떤 Entity들과 Component들의 집합체. 예를들어 도장같은 것.

<ol>

+ 어느정도 규격화된 것들을 의미. 
+ 만들어진 Entity들로 모델로 만들 수 있다. Scene Maker에서 부모 Entity 우클릭, Make Original Model을 누른다. 
+ 만들어진 Model은 Workspace에 My Desk에 만들어져 있다.
</ol>

<div align = center>
 
# Docs
 
 </div>

## ch01

### 제작한 월드 불러오기 및 관리
-
### 워크스페이스
- 폴더 형식의 리소스 관리 공간

<ol>

+ WorkSpace 패널의 기본 위치는 우측 중앙
+ WorkSpace 패널이 보이지 않을때는 Panels - Workspace 를 선택해 열 수 있다.
+ 워크스페이스의 상위 엔트리 3가지가 있다.
+ DefaultPlayer: NativeModel에 있는 Player의 정보를 참조, 실제 생성한 플레이어 아바타 엔티티는 World 안에 속합니다. 시작 시 스타트 포인트에 플레이어 아바타를 생성합니다.
+ BaseEnvironment: MOD 메이커에서 제공하는 기본 MODComponent, MODService, MODLogic, MODEvent가 저장되어있다.
+ MyDesk: 크리에이터가 추가한 리소스, Base Environment에서 확장, 복제한 모델, 컴포넌트 등이 추가된다.
</ol>

- BaseEnvironment

<ol>

+ NativeScripts: Component, Service, Logic, Event가 하위폴더이며, 삭제 불가능합니다. MODComponent는 확장 할 수 있으며 MyDesk 폴더에 저장됩니다.
+ NativeDataSet: MOD 제공하는 기본 DataSet
+ NativeModel: MOD 메이커에서 제공하는 기본 모델들이 저장된 폴더. 모델을 Scene으로 배치해 바로 사용합니다. 확장 모델은 MyDesk 폴더에 저장.
</ol>

- MyDesk
<ol>

+ Workspace는 저장소, SceneMaekr는 작업 현황의 개념입니다.
+ MyDesk에 추가한 리소스를 월드에 배치하면, 씬 메이커 엔티티가 만들어집니다.
+ MyDesk의 원본을 삭제했을 때, 원본 정보를 참조하고 있는 엔티티에서 해당 정보는 지워지지만, 생성된 엔티티는 남습니다.
+ MyDesk에서 바로 배치했던 엔티티라면, 해당 엔티티(리소스)의 이름 옆에 Missing이 붙으며 빨간색으로 변합니다.
+ UIPopup: 팝업 메세지 로직입니다. 필요에 따라 원 로직을 수정하거나 삭제할 수 있습니다.
+ UIToast: 토스트 메시지 로직입니다. 필요에 따라 원 로직을 수정하거나 삭제할 수 있습니다.
</ol>

### 씬 메이커
- 제작 현황을 계층 구조로 된 씬 메이커를 이용해 확인하고, 제작 능률을 높이는 데 사용할 수 있습니다.
- 씬 메이커는 제작 중인 게임 현황을 계층 구조(부모-자식)로 볼 수 있는 패널입니다. 복잡하게 구성한 맵에서 원하는 엔티티를 빠르게 찾을 때 사용하거나, 체계적으로 엔티티를 관리할 때 사용합니다. 가장 상위인 World 계층 아래에 common, maps, ui 엔트리가 있으며 maps와 ui 엔트리는 각자 기본 하위 엔트리를 가지고 있습니다.
- World

<ol>

+ 실제로 제작에 사용한 엔티티들이 모여있으며 가장 상위 계층입니다.
common, maps, ui가 기본 하위 엔트리로 속해 있습니다.
제작 중인 게임의 구성 방식을 확인하고 수정할 수 있습니다.
</ol>

- Common

<ol>

+ 게임 전체에 적용되는 룰을 만들 수 있습니다.
컴포넌트를 추가해 사용합니다.
</ol>

- Maps

<ol>

+ 맵에 배치한 엔티티들은 맵 엔트리 하위에 위치합니다.
map01은 기본 하위 엔트리로 속해있습니다.
</ol>

- UI

<ol>

+ UI 편집기에서 추가하는 엔티티들이 하위에 위치합니다.
DefaultGroup, PopupGroup, ToastGroup이 기본 하위 엔트리로 속해있습니다.
</ol>

- 계층구조

<ol>

+ 단방향으로 영향을 끼친다. 부모->자식
</ol>

- 씬 메이커 검색

<ol>

+ Name: 워크스페이스의 전 영역에서 검색한 이름과 맞는 값을 찾을 때 사용합니다.
+ Component: 엔티티 중 검색어에 해당하는 컴포넌트가 포함된 값을 찾을 때 사용합니다.
</ol>

## ch02

### Entity, Component, Property 
- Entity: MOD 내에서 존재하는 객체이다.

<ol>

+ Entity들이 실제 게임상에서 활동함으로써 시각적으로 보이며, 내부적으로 로직이 돌아가게 된다.
</ol>

- Component: Entity는 Component들로 구성되어 있으며, Component들의 집합체이다.

<ol>

 + Component는 각각의 요소를 담당하며, 각각의 기능을 담당한다.
 + 피자를 예로 들면, 피자는 Entity에 해당되고, 피를 구성하는 토마토, 도우, 소스, 보이지 않는 조리 방법이 Component이다.
 + 이렇게 각각을 Component로 분리하는 이유는 재사용성이 높기 때문이다.  
 ex) 치즈 피자 = 도우 + 소스 + 치즈 + 오븐 조리  
 파인애플 피자 = 도우 + 소스 + 치즈 + 파인애플 + 오븐조리  
 냉동 불고기 피자 = 도우 + 솟 + 치즈 + 불고기 + 전자레인지 조리  
 이렇게 이미 만들어진 Component를 가지고 잘 조합한다면 다른 형태가 나온다.
</ol>

- Property: 각 Component의 세부사항을 설정

<ol>

+ 위의 피자를 예로 들면, 철수는 페퍼로니가 2배 들어있는피자, 영희는 체다치즈가 아닌 모짜렐라 치즈를 원한다면, 철수는 페퍼로니 2배 Component 추가, 영희는 모짜렐라 치즈 Component 추가를 한다.
+ 하지만 재사용성이 떨어지므로 설정이 필요한 항목들을 의미하는게 Property
+ 치즈 Component에는 Size와 치즈 Type이라는 Property
+ 페퍼로니 Component에는 Size라는 Property가 있다면, 같은 Component를 이용해 피자를 만들 수 있다. 물론 각각의 Property는 다르다.
</ol>

### Model
- 나무 Entity를 만들고, Component를 추가하고, Property를 수정해서 원하는 Entity를 만들었다.
- 여러개의 나무를 모아서 숲을 만들고 싶을때, 4개의 나무를 만들면 각각 Entity 생성, Component추가, Property 수정 4번을 해야한다.
- 하지만 이 행위를 100번하면? -> 안된다
- 따라서 이 나무를 찍어내는 도장(Model)을 생성한다.
- 모델화: 많이 찍어내고 싶은 Entity를 모델화 해서 그 모델을 사용한다.
- 모델화는 우클릭 - Make Original Model

### 컴포넌트 추가와 삭제
- Component: 엔티티의 정체성을 결정하는 역할.
- MAP, UI, Player, Etc 4가지 항목이 있다.
- Component 종류  
![component 종류](images/Component%20%EC%A2%85%EB%A5%98.JPG)
- Component 추가 방법

<ol>

+ Property 창 하단의 'Add component'
+ 추가할 컴포넌트를 검색, 선택한다.
+ Property 창에 선택한 컴포넌트가 추가되었는지 확인한다.
</ol>

- Component 초기화
<ol>

+ Context Menu를 열고, 'Reset All Component"를 선택해 컴포넌트의 Property 값을 초기화 한다.  
![Component 초기화](images/%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8%20%EA%B0%92%20%EC%B4%88%EA%B8%B0%ED%99%94.png)
</ol>

- Component 상태 변경
<ol>

 + 컴포넌트는 추가와 동시에 자동으로 활성화 된다.
 + 필요할때 체크박스를 이용해 간단하게 활성 혹은 비활성 상태로 변경이 가능하다.  
 ![Component 상태변경](images/%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8%20%EC%83%81%ED%83%9C%20%EB%B3%80%EA%B2%BD.png)
 + 컴포넌트명 옆에 컨텍스트 메뉴를 열고, 'Disable Component'를 선택해서 비활성화 할 수 있다.
</ol>

- Component 삭제
<ol>

+ 컨텍스트 메뉴를 열고, 'Remove Component'를 선택해 컴포넌트를 삭제한다.  
![Component 삭제](images/%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8%20%EC%82%AD%EC%A0%9C.png)
</ol>

