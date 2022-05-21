<div class = title align = center>


# 1주차

</div>



<div class = body>

<div align = center>
 
# Resources
</div>
 
<div class = chapter>

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
</div>

<div class = chapter>

## 기본 개념의 이해
- 
- 
</div>

<div align = center>
 
# Docs
 
 </div>

<div class = chapter>

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

</div>

<div class = chapter>

## ch02

### Entity, Component, Property
-
### Model
-
### 컴포넌트 추가와 삭제
-

</div>
</div>
