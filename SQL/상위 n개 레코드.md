# 상위 n개 레코드

## 문제설명

<br>

> 📌 `ANIMAL_INS` 테이블은 동물 보호소에 들어온 동물의 정보를 담은 테이블입니다. `ANIMAL_INS` 테이블 구조는 다음과 같으며, `ANIMAL_ID`, `ANIMAL_TYPE`, `DATETIME`, `INTAKE_CONDITION`, `NAME`, `SEX_UPON_INTAKE는` 각각 동물의 아이디, 생물 종, 보호 시작일, 보호 시작 시 상태, 이름, 성별 및 중성화 여부를 나타냅니다.

<br>

---

## 입출력 예

<br>

| NAME |
|------|
| Jack |

## 주의사항

> ※ 보호소에 가장 먼저 들어온 동물은 한 마리인 경우만 테스트 케이스로 주어집니다.


<br>

---

```SQL
SELECT
    A.NAME
FROM
    ANIMAL_INS A
WHERE
    A.DATETIME = (
            SELECT
                MIN(B.DATETIME)
            FROM 
                ANIMAL_INS B);
```
* [프로그래머스](https://school.programmers.co.kr/learn/courses/30/lessons/59405)