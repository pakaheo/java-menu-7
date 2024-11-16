# java-menu-precourse

## 기능 구현 목록

- 목표 : 코치들에게 월~금 5일 간 먹을 메뉴 추천

- 입력
    - 코치 이름
        - 콤마로 구분할 것 **(Done)**
        - 1자 이하, 4자 초과 이름은 입력 불가 **(Done)**
        - 코치 이름은 최소 2글자, 최대 4글자 **(Done)**
        - 코치는 최소 2명, 최대 5명 **(Done)**

    - 카테고리 파일을 입력받는다
        - 카테고리 이름과 메뉴 목록으로 카테고리를 생성한다 **(Done)**

    - 코치별 못 먹는 메뉴
        - 콤마로 구분할 것 **(Done)**
        - 먹지 못하는 메뉴가 없으면 빈 값 입력 **(Done)**

- 메뉴 추천 과정
    - 월요일에 추천할 카테코리를 '랜덤으로' 정함 **(Done)**
        - 카테고리는 Randoms.pickNumberInRange()로 정함 **(Done)**
            - 1 : 일식
            - 2 : 한식
            - 3 : 중식
            - 4 : 아시안
            - 5 : 양식

        - 추천할 수 없는 카테고리일 때는 pickNumberInRange를 재호출 **(Done)**
        - 한 주에 같은 카테고리는 최대 2회까지 **(Done)**
      
    - 각 코치가 월요일에 먹을 메뉴 추천
        - 서로 다른 날에 같은 음식을 먹을 수 없음
        - 카테고리에 있는 메뉴를 Randoms.shuffle()로 섞고 첫 번째 값 사용
            - 메뉴 목록을 List<String>으로 준비
            - shuffle()로 생성된 메뉴 목록을 변경하지 말 것
            - 추천 불가 메뉴일 때는 다시 shuffle
    - 화~금에 대해서도 위 과정 반복
    - 메뉴 추천 완료 시 프로그램 종료