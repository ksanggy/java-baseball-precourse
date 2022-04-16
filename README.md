# 숫자 야구 게임
## 진행 방법
* 숫자 야구 게임 요구사항을 파악한다.
* 요구사항에 대한 구현을 완료한 후 자신의 github 아이디에 해당하는 브랜치에 Pull Request(이하 PR)를 통해 과제를 제출한다.

## 과제 제출 과정
* [과제 제출 방법](https://github.com/next-step/nextstep-docs/tree/master/precourse)

## 기능 구현 목록
1. 상대방 (컴퓨터)이 1~9 서로 다른 수로 이루어진 3자리의 수를 생성한다
2. 게임이 준비 완료 되었고 시작됨을 출력한다
3. "숫자를 입력해주세요" 라는 문구와 함께 사용자 입력을 기다린다
   * 사죵자 입력은 3자리 수로 제한되며 각 숫자는 1~9 만 허용한다
   * 허용되지 않는 입력값이 입력되면 illegalArgumentException을 발생하면서 유저 피드백을 주기위해 짧은 메세지를 출력해준다.
     * 프로그램 종료
4. 입력된 3자리 수를 #1에서 상대방(컴퓨터)가 생성한 3자리 수와 비교한다
   * 같은 자리 + 같은 수 = 스트라이크
   * 같은 수 + 다른 자리 = 볼
   * 같은 수가 전혀 없음 = 낫싱 (NOTHING)
5. 3스트라이크가 될때까지 입력을 계속 받는다
6. 3스트라이크 = 게임 종료 (프로그램 종료)
   * 새로운 게임 시작 또는 종료 선택 제공
     * 1 -> 다시 시작
     * 2 -> 종료
7. Repeat 1 ~ 6

## 제약사항
* 숫자 야구게임을 실행하는 시작점 -> src/main/java > baseball.Application의 main()
* JDK 8 버전 실행
* JDK 제공 Random 및 Scanner API 사용 X
  * camp.nextstep.edu.missionutils 제공하는 Randoms + Console API 사용
    * Random # 추출 -> camp.nextstep.edu.missionutils.Randoms.pickNumberInRange()
    * 사용자 입력 값 -> camp.nextstep.edu.missionutils.Console.readLine()
* src/test/java > baseball.ApplicationTest > 2개 테스트 성공 필수
  * 실패 = 0점처리

* 자바 코드 컨벤션 지키기
* 인덴트 -> 2 depth 넘기 X
  * 1 depth indent 만 허용
    * 예 1) while > if = 2 depth 허용안됨
  * Depth 줄이기 방법 -> 메소드 분리
* stream api 사용하지 않는다
  * lambda 허용
* else 예약어 사용 금지
  * if(조건) { return } 식 방법 사용
  * switch case 금지
* 메소드 코드 길이는 10라인 안넘기
  * Single Responsibility Principle

## 단위 테스트 (요구사항)
* 도메인 로직의 단위테스트 구현
  * UI (System.out, System.in, Scanner) 제외
  * 핵심 로직만 구현
    * MVC 패턴 -> View, Controller 제외하고 Model 에 대한 단위테스트 추가
* JUnit 5 + AssertJ 사용

