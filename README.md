# Bus Seat Manager (버스 좌석 및 대기열 관리 프로그램)

 
## 프로그램 개요
이 프로그램은 버스 탑승 관리 시스템 시뮬레이터입니다.
총 좌석 수가 20석으로 정해진 버스에서 
승객의 교통카드 ID를 통해 승차 및 하차를 관리하고,
좌석이 부족한 경우 대기열을 자동으로 관리하며,
하차 시 대기열 승객을 자동으로 승차시키는 기능을 제공합니다.

### 주요 기능
1) 좌석 수 자동 관리
기본 좌석 수: 20석 (필요 시 수정 가능)

승차 시 좌석 1석 차감 (최소 0석)
하차 시 좌석 1석 증가 (최대 총 좌석 수)

2) 교통카드 ID 기반 탑승 관리
승객마다 고유 교통카드 ID 사용
중복 탑승 및 중복 대기 방지

3) 대기열 기능
좌석이 부족할 경우 대기열로 자동 전환
하차 시 대기열에서 자동으로 승차
대기열은 FIFO(선착순) 방식으로 처리

4) 현재 탑승자 및 대기열 확인 가능

#### 사용법
python
코드 복사
bus = Bus()

# 승차 예시
bus.board_passenger("CARD001")
bus.board_passenger("CARD002")
# 좌석 초과시 대기열 추가
bus.board_passenger("CARD021") 

# 하차 예시
bus.alight_passenger("CARD002")

# 현재 잔여 좌석 수 확인
print(bus.get_available_seats())

# 현재 탑승 중인 승객 리스트 확인
print(bus.get_current_passengers())

# 현재 대기열 확인
print(bus.get_waiting_list())

##### 프로젝트 파일 구조 예시
bash
코드 복사
bus_seat_manager/
│
├── bus.py             # 메인 프로그램 코드
├── README.md          # 프로젝트 설명서
└── requirements.txt   # (필요시 패키지 목록, 현재는 내장 라이브러리만 사용)

###### 개발 환경
Python 3.7 이상

표준 라이브러리만 사용 (외부 패키지 설치 불필요)




