# 2017 Summer GBC Project 
![](https://github.com/0sunzero0/GBC-RUN/blob/main/img/Demo_GBC-Run.gif)
## Project Name: GBC RUN
1. **게임의 스토리**<br>
Ghost 신입회원인 경환이(임시)는 방학을 맞이하여 동아리 프로그램인 GBC에 참여했다. 경환이는 고스트 정식 회원이 되기 위해 열심히 보고서와 과제를 획득한다. 그러나, 열심히 달리지 않으면 경환이는 다음 학기 GBC를 한 번 더 해야한다.  재이수를 먹이기 위해 쫓아오는 매니저를 피해 경환이는 5주간을 버텨야 하는데…! 과연 경환이의 운명은…?

![](https://s3.ap-northeast-2.amazonaws.com/hisbeans-vr/KakaoTalk_20170728_004856366.png)


2. **전체적인 Script 설명** 
	- HPbar – 총 100의 체력으로 tag Enemy와 닿을 때 마다 10씩 줄어들며 체력이 10 줄어들 때 마다 한 칸 줄어든 이미지를 띄우도록 함. tag item1과 닿으면 2씩 체력이 차며 tag item2와 닿으면 10씩 체력이 참. 주인공 오브젝트의 컴포넌트로 넣음. 체력이 다 달면 dead scene으로 넘어감. 

	- item – 일정한 속도로 왼쪽으로 움직임. 스테이지별로 다른 스크립트가 있음 (속도가 달라야 하므로.) collision 컴포넌트를 넣어 충돌을 체크하도록 함. (주인공과 충돌했을 때 HPbar의 체력이 채워질 수 있도록.)tag는 item1, item2.

	- moveBack – 배경 이미지 4개가 왼쪽으로 점점 움직이도록 함. 일정 범위 이상으로 좌표가 넘어가면 맨 뒤에 위치하도록 하여 배경이 계속해서 나올 수 있도록 함. 바닥 속도보다 느리게 하여 공간감을 느낄 수 있도록 하며 스테이지마다 속도가 다름.

	- moveMap – 바닥 이미지 여러개가 왼쪽으로 점점 움직이도록 함. 배경과 마찬가지로 일정 범위가 넘어가면 맨 마지막에 위치하도록 하여 바닥 이미지가 계속해서 나올 수 있도록 함. 스테이지마다 속도가 다름.

	- obs – 장애물 이미지가 왼쪽으로 일정한 속도로 움직이도록 함. 아이템과 똑 같은 속도로 움직이도록 함. collision 컴포넌트를 넣어 충돌체크를 하도록 함. tag 는 Enemy. 

	- ult – 궁극기 아이템이 왼쪽으로 움직이도록 함. 아이템과 같은 속도. collision체크를 해서 주인공과 닿으면 다음 스테이지로 넘어갈 수 있도록 함.(또는 ending scene)

	- ultscreen – 매니저 캐릭터의 컴포넌트로 넣음. 스테이지가 시작할 때 궁극기의 이미지(또는 설명창)가 일정 시간동안 띄워질 수 있도록 함.
	
	- PlayerAction<br>
	A) 1단 점프와 2단 점프 구분<br>
	B) 입력 들어오면 1단 점프 <br>
		B.1) 1단점프 실행시 플레이어 현 위치에서 y축방향으로 jumpPower만큼 증가<br>
	      	B.2) 플레이어의 위치가 0.76f(원래 위치)보다 –0.05f만큼 위치를 감소<br>
      		B.3) 플레이어의 위치가 원래위치 인 경우 원래위치로 jumpOn 실행 중지<br>
	C) 1단 점프하는데 입력 들어오면 2단 점프<br>
	      	C.1) 2단점프 실행시 플레이어 현 위치에서 y축방향으로 jumpPower만큼 증가<br>
		C.2) 플레이어의 위치가 0.76f(원래 위치)보다 –0.05f만큼 위치를 감소<br>
		C.3) 플레이어의 위치가 원래위치 인 경우 원래위치로 doublejumpOn 실행 중지<br>
		
	- start button - 게임 시작을 위한 버튼. button UI로 만들어져 버튼 누를 시, 게임의 첫 번째 단계(first_day scene)으로 넘어간다.
	
	- setting button - 게임 일시정지를 위한 버튼. button UI 사용. 버튼 클릭시 게임 일시정지
	
	- replay button - 게임오버 됐을 경우 뜨는 버튼으로 누를 시 게임의 첫 번째 단계로 넘어간다.


3. **프로젝트의 의의**<br> 
	새로운 프로그램인 unity을 배움과 동시에, 이를 적용할 수 있는 프로젝트. 게임을 활용하여 동아리 회원들과의 친목형성(ex 점수내기) 등을 추구할 수 있을 것이라 생각됨.
