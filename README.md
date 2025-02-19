## 항해 플러스 [ 1주차 과제 ] TDD 로 개발하기

#### 요구사항
point 패키지의 TODO 와 테스트코드를 작성해주세요.

- ✅PATCH /point/{id}/charge : 포인트를 충전한다. 
- ✅PATCH /point/{id}/use : 포인트를 사용한다.
- ✅GET /point/{id} : 포인트를 조회한다.
- ✅GET /point/{id}/histories : 포인트 내역을 조회한다.
- ✅잔고가 부족할 경우, 포인트 사용은 실패하여야 합니다.
- 동시에 여러 건의 포인트 충전, 이용 요청이 들어올 경우 순차적으로 처리되어야 합니다.
<br>

#### `Default`

- ✅`/point` 패키지 (디렉토리) 내에 `PointService` 기본 기능 작성
- ✅`/database` 패키지의 구현체는 수정하지 않고, 이를 활용해 기능을 구현
- ✅ 각 기능에 대한 단위 테스트 작성

총 4가지 기본 기능 (포인트 조회, 포인트 충전/사용 내역 조회, 충전, 사용) 을 구현합니다.
```java
[PATCH] localhost:8080/point/1/charge
        
{
    "id": 1,
    "point": 1000,
    "updateMillis": 1727284566542
}

[PATCH] localhost:8080/point/1/use
        
{
    "id": 1,
    "point": 500,
    "updateMillis": 1727284599015
}

[GET] localhost:8080/point/1
        
{
    "id": 1,
    "point": 500,
    "updateMillis": 1727284599015
}

[GET] localhost:8080/point/1/histories

[
    {
        "id": 1,
        "userId": 1,
        "amount": 1000,
        "type": "CHARGE",
        "updateMillis": 1727284566542
    },
    {
        "id": 2,
        "userId": 1,
        "amount": 500,
        "type": "USE",
        "updateMillis": 1727284599015
    }
]


```

#### `Step 1`

- ✅ 포인트 충전, 사용에 대한 정책 추가 (잔고 부족, 최대 잔고 등)
-  동시에 여러 요청이 들어오더라도 순서대로 (혹은 한번에 하나의 요청씩만) 제어될 수 있도록 리팩토링
-  동시성 제어에 대한 통합 테스트 작성
    
    

#### `Step 2`

- 동시성 제어 방식에 대한 분석 및 보고서 작성 ( **README.md** )

## 추가 과제 - STEP2. 동시성 제어 방식에 대한 분석 및 보고서 작성

<br><br><br><br><br><br><br><br>
----
#### 커밋태그

| 태그       | 설명                                 |
|:---------|:----------------------------------------|
| feat     | 새로운 기능 추가                          |
| fix      | 버그 수정                                 |
| refactor | 코드 리팩토링                             |
| comment  | 주석 추가(코드 변경 X) 혹은 오타 수정      |
| docs     | README와 같은 문서 수정     |
| merge    | merge                                      |
| rename   | 파일, 폴더 수정, 삭제 혹은 이동            |
| report   | 해당 주차별 과제 등록 및 풀이               |
| chore    | 설정 변경                                   |
