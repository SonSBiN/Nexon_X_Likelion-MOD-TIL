<div class = title align = center>

# 5주차

</div>

<br></br>

<div align = center>
 
# Resources
</div>
 
### 컴포넌트의 활용 I
- MOD에서 자주 사용하는 컴포넌트 실습
- dafault player (캐릭터)
<ol>

- RigidBodyComponent:캐릭터의 움직임  
하향점프  
중력값   
isblockvirtical: 다른 지형의 발판정보에 막히는것  
IsolatedMove: 낭떨어지에서 막혀서 못떨어지게 함  
MASS: 질량, 질량이 클수록 보존하는 힘이 커져서 가속이 늦게붙음  
IsQuarterView: 게임의 방식을 위아래 구분없이 수평,수직으로 구분함
- TriggerComponent: 물체의 충돌  
Enter: 충돌시, Stay:출돌하는 동안, Leave: 충돌이 끝났을때  
self.entity.enable = false 아이템을 먹은것처럼 하는것 (사라지게함)
- SpriteRendererCompoennt: 대표적인 display Component. Sprite가 아닌 비슷한 것을 수행하는 component가 존재한다. 
- WebSpriteComponent: 웹에 있는 이미지를 경로를 따와서 가져올 수 있다. 애니메이션도 설정 가능
- YoutubeComponent: 유튜브의 주소를 가져오면, 해당 영상을 스트리밍 해준다.
- AvatarRendererComponent, CostumeManagerComponent: 캐릭터의 옷,피부, 등을 설정할 수 있는 Component 

</ol>


### 컴포넌트의 활용 II
- 

<br></br>
<br></br>

<div align = center>

# Docs
 
 </div>

## ch09

### 엔티티의 충돌을 감지하는 TriggerComponent
- 2주차 내용과 동일
### 원하는 이미지 갖고 오기
- 게임에 필요한 이미지 리소스를 찾아 메이커에 활용한다.
- 

<br></br>

## ch10

### InputService를 활용한 입력과 액션
-
### 공격과 피격
-
### 스킬 이펙트를 뿌려보자!
-
