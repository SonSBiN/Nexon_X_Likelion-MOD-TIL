<div class = title align = center>

# 6주차

</div>

<br></br>

<div align = center>
 
# Resources
</div>
 
## UI에디터의 이해
- UI는 유저와 클라이언트가 소통을 할 수 있는 매개체
- UI TransfromComponent: 모바일에서 조이스틱같은 것들을 정렬기능을 통해 해상도가 바뀌더라도 고정된 위치에 할 수 있도록 한다.
- buttonComponent: 버튼기능을 하게해주는 component
- UI그룹을 만들어놓고 작업을 하게되면 편리하게 할 수 있음. DefaultGroup안에서 Enable이 꺼져있으면 다른 그룹 내 UI들도 꺼져있다.
- UI같은 경우는 각 Client에만 생성이되어있어서, 서버에는 존재하지 않는다. (Client Only)
- SpriteGUIRendererComponent 에서 FillAmount 값을 설정하면 HP/MP/경험치 등이 차오르는것을 연출할 수 있다. (Type이 fill타입이어야 한다.) (Background에 UI를 같은걸로 하나 더 추가해서 배경까지)
- 만약 Type이 다르넋이라면, pivot을 사용하면 되는데, 이것이 원점이 된다. Pivot의 X를 0으로 바꾸면 왼쪽으로 정렬이되어, width값을 조정해주면 같은 연출을 할 수 있다.
- ScrollLayOutComponent: 인벤토리처럼 규격화된 것으로 만들 수 있게 해주는 컴포넌트. Type을 grid로 바꿔주면 된다.

## 알아두면 유용할 것들
- 

<br></br>
<br></br>

<div align = center>

# Docs
 
 </div>

## ch11

### UI 에디터 활용과 제어
- UI 에디터에서 버튼, 이미지, 스프라이트, 스크롤 뷰 같이 기본적인 UI들을 배치할 수 있고, 각 엔티티들을 구성하여 인벤토리나 상점 UI를 제작할 수 있다.
- UI 엔티티 생성
<ol>

- UI 엔티티 생성에는 두가지 방법이 있다.
1. 기본 UI 모델을 선택해 배치한다. - 화면 왼쪽의 기본도구를 사용해 버튼, 이미지 등 UI엔티티를 배치해 특정 기능을 수행하는 인벤토리, 스킬창 UI를 만들 수 있다.
2. UI 프리셋을 활용한다. - UI 에디터는 게임에서 자주 사용하는 UI를 프리셋으로 만들어 제공하고 있습니다. 프리셋의 인벤토리, 상태창, 랭킹 UI 등을 배치한다면, 기본 UI 엔티티를 이용해 복잡한 구조를 하나하나 만들 필요 없이 UI를 빠르게 배치할 수 있습니다.  
- UI 모델  
![UI Model](images/UI%20Model.PNG)  
</ol>

- UI Preset
<ol>

- 기본 UI 엔티티를 이용해 필요한 UI를 매번 제작하려면 많은 시간을 투자해 반복 작업을 해야 합니다. 효율적인 작업을 위해 MOD에서는 게임에서 통용되는 UI를 프리셋 형태로 제공하고 있습니다.
- UI 프리셋은 UI 편집 모드로 씬 창이 변경되면 Model LIst 창에 UI Preset 리스트가 열립니다. 프리셋에는 UI와 알맞은 스크립트가 함께 포함되어 있습니다.Scene에 프리셋을 배치한 뒤, UI와 스크립트는 제작 중인 게임에 맞게 수정해 사용할 수 있습니다.
</ol>

- 스크립트를 이용한 UI 엔티티 제어
<ol>

- UI 엔티티도 엔티티이기 때문에 스크립트에서 각 엔티티에 접근할 때 월드 상의 엔티티와 동일한 방법으로 접근이 가능합니다.
월드의 엔티티를 스크립트에서 접근, 참조하는 방법과 동일하게 사용할 수 있습니다.
UI 엔티티에 포함된 컴포넌트 역시 기존 컴포넌트와 같은 방법으로 참조할 수 있습니다.
- UI 엔티티는 클라이언트 공간에서만 존재하므로 서버에서는 접근할 수 없습니다. 따라서 UI 엔티티나 엔티티의 컴포넌트를 받아올 때는 오직 클라이언트 함수에서만 참조해야 합니다. 서버에서 처리된 내용을 UI로 출력하거나 UI를 통해 입력한 내용을 서버에서 처리해야 할 때는 실행제어를 이용해 각 공간에서 액션을 수행하도록 해야합니다.  
![UI script](images/UI%20Script.PNG)
- UI 스크립트 예시  
1. 버튼을 클릭 했을 때, 서버에서 처리를 요청하는 예시코드  
![UI script 예시1](images/UI%20script%20%EC%98%88%EC%8B%9C1.PNG)  
2. 서버에서 처리 결과를 UI로 출력할 때의 예시 코드  
![UI script 예시2](images/UI%20script%20%EC%98%88%EC%8B%9C2.PNG)
</ol>

- UI 노출처리
<ol>

- 스크립트에서 UI 노출 설정은 Entity 함수인 SetEnable을 이용한다.  
![UI 노출 예시코드](images/UI%20%EB%85%B8%EC%B6%9C%EC%84%A4%EC%A0%95%20%EC%98%88%EC%8B%9C%EC%BD%94%EB%93%9C.PNG)  
- 다만 특정 UI를 구성하고 있는 엔티티들이 계층 구조로 묶여있지 않고 동일한 계층으로 생성되어 있다면, 모든 엔티티의 노출 및 숨김 처리를 상황마다 일일이 처리 코드를 작성해야 하므로 상당히 비효율적입니다. 동일 계층인 여러 엔티티가 같은 순간에 나타났다 사라져야 한다면, 모든 엔티티의 Enable 설정을 작성해야 합니다.  
- 작성 실수를 방지하고, 시간을 효율적으로 사용하기 위해 UI 구성은 계층 구조를 적극적으로 활용하는 것이 좋습니다. 부모 엔티티가 자식 엔티티에 일방향으로 영향을 끼치는 계층 구조 특성을 이용합니다. 특정 UI 엔티티를 최상위 부모 엔티티로 정해 계층 구조를 만들고, 나머지 엔티티는 자식으로 포함시킵니다. 부모 엔티티만 참조한다면 짧게 작성할 수 있고 실수를 방지 할 수 있습니다.  
- 토스트 메시지 UI를 기본 UI엔티티를 이용해 만들었다면 모두 동일한 계층에 따로따로 존재합니다. 이 중 바탕 이미지를 최상위 부모 엔티티로 만들고, 토스트 메시지를 구성하고 있는 다른 UI 엔티티는 자식 엔티티로 만들어 계층 구조를 완성합니다. 스크립트에서 노출/숨김 처리를 작성할 때 부모 엔티티만 적용해도, 자식 엔티티에 동일하게 적용됩니다.  
![UI 노출설정 계층구조 예시](images/UI%20%EA%B3%84%EC%B8%B5%EA%B5%AC%EC%A1%B0%20%EB%85%B8%EC%B6%9C%EC%84%A4%EC%A0%95.PNG)
</ol>

- UIGroupt을 활용한 UI관리 및 제어
<ol>

- UI를 효율적으로 관리해야 제작 중 필요한 UI를 빠르게 찾을 수 있고, 게임 제작 구조를 체계적으로 관리할 수 있을 것입니다. UIGroup은 기능 별로 연관된 기능이 있는 UI 엔티티끼리 묶어 관리할 수 있습니다. 메이커에서는 맵 레이어처럼 보이며, 기능 개념은 폴더에 가깝습니다.  
![UI 그룹 편집](images/UI%20%EA%B7%B8%EB%A3%B9%20%ED%8E%B8%EC%A7%91.PNG)
- UIGroupt단위 별 제어
1. UIGroup별 노출 및 숨김 처리: 스크립트를 활용해 UIGroup 단위 별로 노출 혹은 숨김 처리가 가능합니다. UIGroup도 엔티티이기 때문에 엔티티의 SetEnable 함수를 이용해 제어할 수 있습니다.  
![UI 그룹제어 예시코드](images/UI%EA%B7%B8%EB%A3%B9%EC%A0%9C%EC%96%B4%20%EC%98%88%EC%8B%9C%EC%BD%94%EB%93%9C.PNG)
2. UIGroup 상시 노출 설정: UIGroup에 포함되어 있는 UIGroupComponent의 DefaultShow를 이용해 해당 UIGroup에 속한 UI엔티티들의 상시 노출 여부를 설정할 수 있습니다.
DefaultGroup의 경우 DefaultShow 기본값이 trueEditbox_Check이지만, 다른 UIGroup은 DefaultShow 기본값이 false이므로 상시 노출로 변경하고 싶다면 true로 변경해야합니다.
</ol>

### UI 입문! 텍스트와 이미지
- DefaultGroup: 항상 활성화 되어 있는 UI그룹. 채팅창이나 공격, 점프와 같은 필수적인 버튼은 DefaultGroup에 배치된다.
- UI를 만들어서 배치하더라도, DefaultGroup 과 달리 사용자가 추가한 UIGroup은 프로퍼티 에디터나 스크립트를 통해 수정해주지 않으면 기본적으로 보이지 않는 상태이다.

<br></br>

## ch12

### 캐릭터 초기 속성 편집
-
### Model
-
### 아이템 생성 및 삭제
-
