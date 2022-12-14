# 미션 - 다리 건너기
![App Screenshot](../bridge.jpg)

## Project Structure

프로젝트 구조는 다음과 같습니다.

    .
    ├── controller
    │   └── BridgeGame.js
    ├── model
    │   └── Bridge.js
    ├── utils
    │   ├── constant.js
    │   └── validation.js
    ├── view
    │   ├── InputView.js
    │   └── OutputView.js
    ├── App.js
    ├── BridgeMaker.js
    └── BridgeRandomNumberGenerator.js

- App.js

    프로젝트를 실행하는 역할. 게임에 필요한 BridgeGame 객체와 Bridge 객체를 생성하기 위해 유도한다.

- BridgeMaker.js

    Bridge 객체를 만들 때 사용할 객체다. 랜덤 생성된 숫자가 1이면 U, 0이면 D를 돌려준다.

- BridgeRandomNumberGenerator.js

    랜덤 숫자를 생성하는 객체다. 0 또는 1을 생성

- BridgeGame.js

    다리 건너기 게임을 관리하는 객체. Bridge를 어떻게 조작할 지에 집중한다.

- Bridge.js

    다리의 정보를 담고 있는 객체. 몇번 째 칸 까지 도달했는지, 다음 칸으로 건너기, 현재 상태 지도 업데이트 기능도 들어있다. 단, 스스로 판단하기 보다 외부에 있는 BridgeGame의 명령을 받아 움직이도록 설계되어있다.

- InputView.js

    입력을 담당하는 함수


- OutputView.js

    출력을 담당하는 함수

- constant.js

    변수의 상수를 담당해줄 함수. 수정 금지!

- validation.js

    입력 값에 대한 검증을 담당한다.


## 🎖️ 기능 목록
- [x] 다리 길이 입력받는 기능

    자동으로 생성할 다리 길이를 입력 받는다. // readBridgeSize()

    - [x] 다리 길이 검사기능 구현 
    
        3 이상 20 이하의 숫자를 입력할 수 있으며 올바른 값이 아니면 예외 처리한다. // isBridgeSizeValid()

- [x] 전달 받은 사이즈 만큼의 다리를 생성하는 기능

    전달 받은 사이즈 만큼의 다리를 생성한다. // Bridge()

    - [x] makeBridge()
        
        생성한 랜덤 번호에 따라서 bridge 배열에 'U' 혹은 'D'을 추가한다.

- [x] 플레이어가 이동할 칸을 입력받는 기능

    라운드마다 플레이어가 이동할 칸을 입력 받는다. //readMoving()
    
    - [x] 사용자가 움직이기 위해 입력한 글자가 U 혹은 D 인지 검사하는 기능

        U(위 칸)와 D(아래 칸) 중 하나의 문자를 입력할 수 있으며 올바른 값이 아니면 예외 처리한다. // isUserMovingInputValid()

- [x] 다리를 끝까지 건너면 게임이 종료하는 기능


- [x] 게임 재시작/종료 여부를 입력 받는 기능
    게임 실패 후, 게임 재시작/종료 여부를 R,Q로 입력 받는다. //  readGameCommand()
    
    - [x] 사용자가 입력한 값이 R 혹은 Q인지 검사하는 기능
        R(재시작)과 Q(종료) 중 하나의 문자를 입력할 수 있으며 올바른 값이 아니면 예외 처리한다. //isGameCommandValid()

- [x] 게임의 승리/패배 판정 기능

    다리의 끝까지 도달했을 때, 혹은 실패했을 때를 감지하는 기능

- [x] 게임 시작 문구

    게임 시작이 됐음을 출력하여 알린다. // printGameStart() 

- [x] 게임 종료 문구

    게임 종료 문구 출력 기능 // printResult() 

- [x] 사용자가 이동할 때마다 다리 건너기 결과의 출력하는 기능

    사용자가 이동할 때마다 다리 건너기 결과를 출력한다. //printMap()
    - 이동할 수 있는 칸을 선택한 경우 O 표시
    - 이동할 수 없는 칸을 선택한 경우 X 표시
    - 선택하지 않은 칸은 공백 한 칸으로 표시
    - 다리의 시작은 [, 다리의 끝은 ]으로 표시
    - 다리 칸의 구분은 |(앞뒤 공백 포함) 문자열로 구분
    - 현재까지 건넌 다리를 모두 출력

- [x] printError()

    예외 상황 시 에러 문구를 출력해야 한다.
    단, 에러 문구는 "[ERROR]"로 시작해야 한다.

## 🔎 1~3주차 공통 피드백 내용

### 1주차
- 요구사항을 정확히 준수한다
- 커밋 메시지를 의미 있게 작성한다
- git을 통해 관리할 자원에 대해서도 고려한다
- Pull Request를 보내기 전 브랜치를 확인한다
- PR을 한 번 작성했다면 닫지 말고 추가 커밋을 한다
- 이름을 통해 의도를 드러낸다
- 축약하지 않는다
- 공백도 코딩 컨벤션이다
- 공백 라인을 의미 있게 사용한다
- space와 tab을 혼용하지 않는다
- 의미 없는 주석을 달지 않는다
- linter와 Code Formatter의 기능을 활용한다
- EOL(End Of Line)
- 불필요한 console.log를 남기지 않는다
- JavaScript에서 제공하는 API를 적극 활용한다


### 2주차
- README.md를 상세히 작성한다
- 기능 목록을 재검토한다
- 기능 목록을 업데이트한다
- 값을 하드 코딩하지 않는다
- 구현 순서도 코딩 컨벤션이다
- 한 함수가 한 가지 기능만 담당하게 한다
- 함수가 한 가지 기능을 하는지 확인하는 기준을 세운다
- JavaScript에서 객체를 만드는 다양한 방법을 이해하고 사용한다.
- 테스트를 작성하는 이유에 대해 본인의 경험을 토대로 정리해본다
- 처음부터 큰 단위의 테스트를 만들지 않는다


### 3주차
- 함수(메서드) 라인에 대한 기준
- 발생할 수 있는 예외 상황에 대해 고민한다
- 비즈니스 로직과 UI 로직을 분리한다
- 객체의 상태 접근을 제한한다
- 객체는 객체스럽게 사용한다
- 필드의 수를 줄이기 위해 노력한다
- 성공하는 케이스 뿐만 아니라 예외에 대한 케이스도 테스트한다
- 테스트 코드도 코드다
- 테스트를 위한 코드는 구현 코드에서 분리되어야 한다
- 단위 테스트하기 어려운 코드를 단위 테스트하기
