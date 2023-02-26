> 참고
> [이것이 MySQL이다.](http://www.yes24.com/Product/Goods/90118480)

## 0.DBMS와 MySQL 소개

**_MySQL은 DBMS 소프트웨어(=프로그램)_** 일종으로 Oralce사에서 제작한 툴이다.
[참고자료1](https://velog.io/@98kimjh/Database-DBMS-Concept)
[참고자료2](https://velog.io/@susan9905/%EA%B3%84%EC%B8%B5%ED%98%95-%EC%BF%BC%EB%A6%AC)
[참고자료3](https://velog.io/@yeomyaloo/%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4-%EA%B0%9C%EB%85%90-%EC%9E%A1%EA%B8%B0-1.-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4)
[참고자료4](https://computer-science-student.tistory.com/194)

## 1.1 DBMS 소개

### 데이터베이스의 정의와 특징

**_데이터베이스를 '데이터의 집합'_** 이라고 정의하며 데이터베이스는 **여러명의 사용자**나 응용프로그램이 공유하고 **동시에 접근**이 가능해야 한다. 그래서 Excel과 같은 프로그램은 데이터의 집합으로 사용할수 있지만 동시에 접근을 할 수가 없기때문에 DBMS라고 부르기 어렵다.

> 데이터베이스는 '데이터의 집합' 혹은 '데이터의 저장공간'이며, 이 데이터베이스를 운영하는 소프트웨어를 DBMS라고 한다.

![](https://velog.velcdn.com/images/bini/post/9893f6de-1ee7-4041-b167-e2c085f02e10/image.png)

DBMS에는 MySQL말고 다양한 소프트웨어 종류들이 많다. 아래의 표로 확인하보자.

| DBMS       | 제작사     | 운영체제                  | 기타                        |
| ---------- | ---------- | ------------------------- | --------------------------- |
| MySQL      | Oracle     | Unix, Linux, Windows, Mac | 오픈소스(무료), 상용        |
| MariaDB    | MariaDB    | Unix, Linux, Windows      | 오픈소스(무료)              |
| PostgreSQL | PostgreSQL | Unix, Linux, Windows, Mac | 오픈소스(무료)              |
| Oracle     | Oracle     | Unix, Linux, Windows      | 상용시장 점유율 1위         |
| SQL Server | Microsoft  | Windows                   |                             |
| Access     | Microsoft  | Windows                   | PC용                        |
| SQLite     | SQLite     | Android, ios              | 모바일 전용, 오픈소스(무료) |

그럼 이제 DBMS의 특징에 대해 살펴보자.

- 데이터의 무결성: DB안의 데이터는 오류가 있으면 안된다.
- 데이터의 독립성: DB의 저장소를 바꾸고 구성을 바꾼다고 해도 응용프로그램 코드는 변경이 되어서는 안된다.
- 보안: 사용자계정에 따라 데이터 접근을 허가할지 말지를 결정하며 허가된 사용자더라도 서로 각각 다른 권한을 가져야 한다.
- 데이터 중복의 최소화
- 응용프로그램 제작 및 수정이 쉬워짐
- 데이터의 안전성 향상: DBMS가 제공하는 백업 및 복원기능으로 데이터의 안전성을 높일 수 있다.

### 1.1.2 데이터베이스의 발전

- 오프라인으로 관리: 컴퓨터가 없었던 시절, 장표같은 걸로 관리하였다.
- 파일시스템 이용: 메모장이나 엑셀같은 프로그램을 통해 소량의 데이터를 관리하기 시작하였다. 하지만 데이터가 많아지면서 파일의 크기가 커지면서 문제발생 우려가 발생하기 시작하였다.
- 데이터 베이스 관리시스템: 대량의 데이터를 보다 효율적으로 관리하고 운영하기 위해 DBMS가 나오기 시작했으며 DBMS에 데이터를 구축하고 관리하고 활용하기 위해서 사용되는 언어가 SQL이다.

### 1.1.3 DBMS 분류

이 내용은 크게 중요한 내용은 아니지만 면접간에 물어볼수도 있을수도 있으니 한번 확인해보자.

DBMS는 크게 계층형, 망형, 관계형, 객체지향형, 객체관계형으로 구분이 된다. 그중에 우리가 공부할 MySQL은 관계형 DBMS로 RDBMS라고 불린다.

#### 계층형 DBMS

계층형 DBMS는 트리구조 형태로 되어 있으며 1:N 관계를 가진다. 이 구조는 처음 구축 후에 그 구조를 변경하기 까다로우며 주어진 상태에서의 검색은 상당히 빠르지만 접근의 유연성이 부족해서 임의의 검색에는 어려움이 따른다.

![](https://velog.velcdn.com/images/bini/post/2e0fbb98-850d-4400-98cb-816bfec01304/image.png)

#### 망형 DBMS

거의 사용될 일이 없지만 한번 알아보면 망형 DBMS는 계층형 DBMS에 비해 노드간에 수평적으로도 연결이 되어 있다는 것이다.

![](https://velog.velcdn.com/images/bini/post/1301b4ae-3455-4ad6-b1a1-b8e947035dc8/image.png)

#### 관계형 DBMS

RDBMS의 특징은 **테이블이라는 최소단위**로 구성되어 있다. 테이블을 살펴보면 행과 열로 나눠지는데 행은 row라고 불리며 데이터의 개수와 같다. 열은 컬럼이라고 불리며 필드라고도 불린다.

![](https://velog.velcdn.com/images/bini/post/903933a5-641b-4b48-82c1-850f7f799b40/image.png)

### 1.1.4 SQL 개요

RDBMS를 운영 및 유지하기 위해 필요한 언어를 SQL이라고 한다. SQL의 특징은 다음과 같다.

- DBMS 제작회사와 독립적이다.
  - 표준 SQL이라는것을 기반으로 DBMS 벤더 사마다 특징적인 SQL을 추가하여 개발하였다.
- 다른 시스템으로 이식성이 좋다.
- 표준이 계속 발전한다.
- 대화식 언어이다.
- 분산형 클라이언트/서버 구조이다.

## 1.2 MySQL 소개

MySQL은 Oracle사에서 제작한 DBMS 소프트웨어로 오픈소스로 제공한다.

> MySQL은 비상업용이나 교육용으로는 제한없이 사용이 가능하지만 상용으로 사용하기 위해서는 상용 라이선스를 취득해야한다.

> 만약 상용으로도 무료로 사용하고 싶으면 MySQL 개발자가 만든 MariaDB를 공부하는것도 좋다.
