<div class = title align = center>

# 2주차
</div>

<div align = center>
 
# Resources
</div>
 
## 기본 컴포넌트의 이해
- 자세한 사항들은 개발자의 API Reference에서 살펴볼 수 있다.
- 자주쓰는 Component는 별도의 영상
- 특수하고 자주쓰는 Component
- Transform Component: 거의 모든 엔티티에 쓰인다.
<ol>

+ 특수한 형태를 제외하고는 대부분의 엔티티에 쓰인다.
+ 위치정보를 가지고 있다.
+ Position: 어떠한 좌표를 가지는지. 실제로 x,y,z의 값이라 보면 된다. 값을 바꾸면 위치가 이동함
+ Scale: 이 물체의 크기를 나타낸다. (비율) 1이 기본값. x의 값을 2배로 하면 가로로 2배로 늘어난다.
+ Rotation: 회전값 대부분의 수직게임에서는 z축으로 회전된다. (시계,반시계 방향 등. 단위는 degree( ˚ )
+ 매우 자주 사용하고, 아주 중요한 Component
+ 만약 부모-자식 엔티티로 될 경우, 자식 엔티티는 부모 엔티티의 상대좌표로 Position이 설정 된다. (상대좌표)
+ WorldPosition: 위 같은 경우, WolrdPosition은 World 기준의 좌표이다. (절대좌표)
+ Rotation도 마찬가지. 그냥 Rotation은 부모기준 상대좌표, World Rotation은 World 기준 절대좌표
</ol>

- SpriteRendererComponent: '무엇'을 그릴것인가. 어떤 이미지를 그릴것인가를 표시해주는것. 어떤걸 어떻게 표시할지, 그려질지 나타내는 Component. Transform과는 다르게 없을 수 있음.
<ol>

+ SpriteRUID: 이 값이 해당 이미지를 상징하는 값이라고 생각하면 된다.
+ 외부의 이미지도 import하면 RUID가 발급이된다.
+ 기본적으로 이미지이지만, 애니메이션도 포함되는 ID이다.
+ PlayRate: 애니메이션의 속도를 지정 가능.
+ StartFrameIndex, EndFrameIndex: 애니메이션이 연속적으로 나오는 이미지들인데, 이것들을 몇번부터 몇번까지만 재생하는지 설정하는것.  
인덱스 이상의 값 설정시, 가지고 있는 인덱스까지만 실행한다.
+ FlipX, FlipY: X축 반전, Y축 반전 (이미지 클릭시 나오는 점을 기준으로 반전)
+ Layer: 2D게임이므로 이미지의 앞,뒤 순서를 뜻함. 다음강의에서 진행
+ Color: 색을 입하는것.
+ DrawMode: 기본적으로 Simple. Tile로 변경시 TileSize를 통해 사이즈 지정 가능.
+ TileSize: X와 Y의 값만큼 늘려준다. 
</ol>

## 지형과 레이어의 이해
- MOD에서 구성하는 방법은 메이플스토리에서 구성하는 방식과 동일함.
- 직사각형의 그리드가 있다.  
 그리드의 교점: 작은 크기의 타일  
 그리드의 중점: 큰 크기의 타일  
 사각형 타일들의 대각선을 클릭하면 대각선의 지형을 만들 수 있다.
- World/maps/map01/TileMap 엔티티가 있다.  
클릭시 타일맵 Property가 나오고, TileMapComponent가 나온다.
- TileMapComponent
<ol>

+ Color: 타일의 색상 정할 수 있다.
+ TileSetRuID: Sprite Picker에서 다른 타일들로 바꿀 수 있다.
+ ooLayer: 이미지의 앞,뒤 순서를 정한다.
</ol>

- FootHold: 캐릭터, 몬스터들이 밟는 발판 정보
<ol>

+ 좌측상단 File/Setting/만들기/발판 정보 체크 -> Scene안에서 발판정보 확인 가능하다.
+ FootHold Model에 포함된 FootHold들은 수정이 가능하다. 추가/삭제도 가능.
+ Property에서도 수정가능하다.   CustomFootholdComponet에서  
size: 각 Foothold Point의 갯수  
목차를 열어보면 각 풋홀드의 포인트들의 좌표를 설정할 수 있다.
+ FootHoldDrag: Tilemap의 마찰력
+ FootHoldForce: Tilemap이 플레이어에 가하는 힘
+ FootHoldWalk: Tilemap 위에 있을때의 속력
</ol>

- MapLayer: 다른 Tile들을 쓸수있는 Map들의 Layer
<ol>

+ 하나의 맵에는 최대 10개의 Layer 추가 가능. 
+ Layer1에 구성하고있는 Entity를 Layer2로 옮기고 싶다면, 그 Entity의 Property->SpriteRendererComponent->SortingLayer에서 원하는 Layer로 변경한다.
+ Layer에서 가장 위에 위치한 Layer가 가장 앞에 위치한다.
</ol>

## 자주 사용하는 컴포넌트
- TweenLineComponent
<ol>

+ Model이 이동하는 Component
+ TweenType: 등속운동인지, 가속운동인지, 등가속운동인지 등등을 설정해준다.
+ SyncType (동기화 방식): Server는 여러 클라이언트에서도 동일하게 움직인다. Client는 시간이 안맞을 가능성이 높다.  
동기화가 되는 객체가 충돌이 발생하거나, 타거나 하는 것들은 Server로 설정을 해주어야한다.
</ol>

- TweenCirculerComponent, TweenFloating Component
<ol>

+ 기본적으로 TwwenLineComponent와 동작 과정이 비슷하고, Circular는 원형운동 Floating은 상하운동이 동작한다.
</ol>

+ RigidbodyComponent
<ol>

+ 강체(형태가 변하지 않는 (고체 등)) 물체들의 물리 운동들을 컨트롤 하는것.
+ 플레이를 했을때 낙하법칙에 의해 떨어지는 효과 등
+ IsBlockVertical: 세로 지형은 무조건 Block 되는것.
+ IsQuaterView: 지형이 없을때 떨어지는게 아니라, 공중을 날듯 자유롭게 이동 가능하게 한다. (3D 입체의 배경에서는 자유롭게 움직이는것처럼 보인다.)  
QuaterView() 에서는 가속도 등 자유롭게 설정 가능.
</ol>

- MovementCoponent
<ol>

+ InputSpeed: 해당 Model의 Speed값 조정 가능.
+ JumpForce: 해당 Model의 Jump값 조정 가능.
</ol>

- TriggerComponent: 객체간에 충돌이 있을때 알려주는 Component
<ol>

+ ColliderOffset: 캐릭터의 박스 사이즈를 변경할 수 있다.
+ 물리적인 특성이 없으므로 바로 Event가 일어나지 않지만, Script에서 받아서 설정해주면 발생한다.
</ol>

- PlayerComponent:
<ol>

+ 플레이어들의 MaxHp, PVPMode 설정 가능하다.
</ol>
 <br></br>
 <br></br>
<div align = center>
 
# Docs
</div>

## ch03
### 엔티티의 위치, 크기, 회전 조정
### 스프라이트 색상 조정
## ch04
### 발판 만들기
-
### 맵 레이어
- 

## ch05
### 엔티티 구간 이동시키기
### 캐릭터 초기 속성 편집
### 엔티티의 충돌을 감지하는 TriggerComponent