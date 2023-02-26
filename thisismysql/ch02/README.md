> 참고
> [이것이 MySQL이다.](http://www.yes24.com/Product/Goods/90118480)

# 2. MySQL 설치

## 2.1 MySQL 설치 전 준비사항

이제 MySQL8 버전을 설치해보자. 나는 현재 Mac 환경이므로 책과는 조금 다르게 설치해볼 예정이다.

## 2.2 🍺 Homebrew 설치

먼저, homebrew부터 설치해보자.

먼저 [홈브류](https://brew.sh/index_ko) 사이트에 들어가서 아래 명령어를 copy 해오자.

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

copy해온 명령어를 iterm2나 기본 터미널에 붙여넣어서 설치해보자.

설치가 제대로 되었다면 아래 그림과 같이 brew를 치면 설명서가 나올 것이다.

![](https://velog.velcdn.com/images/bini/post/a26c2a8c-1ed3-4492-b71f-720c4338920a/image.png)

## 2.3 MySQL 설치

이제 설치한 homebrew 명령어를 통하여 mysql을 설치해보자.

```shell
brew install mysql
```

위와 같이 명령어를 입력하자.

그리고 좀 기달리면 설치가 완료되었을 것이다.

이제 mysql을 시작해보자.

```shell
brew services start mysql
```

그리고 다음 명령어를 통하여 mysql을 접속해보자.

```shell
mysql -uroot
```

그러면 mysql 콘솔창이 등장할텐데 이제 비밀번호를 설정해보자.

```sql
mysql_secure_installation
```

여기서 VALIDATE PASSWORD PLUGIN 설치여부 물어볼 때는 N(아니오)를 선택하면 된다. 그리고 원하는 비밀번호를 설정 후 mysql 콘솔창을 exit 명령어를 통하여 나오자. 그리고 재접속해보자.

```shell
mysql -uroot -p
```

그리고 설정한 비밀번호를 입력후 접속하면 아래와 같이 나온다.

![](https://velog.velcdn.com/images/bini/post/b4af0f6d-3741-4bef-8181-6df6ca9f36f1/image.png)

## 2.4 DataGrip 설치

이제 mysql을 콘솔이 아닌 에디터로 편리하게 해주는 DataGrip을 설치해보자.

보통은 mysql workbench를 설치하지만 나는 jetbrain 기반 툴을 선호하기때문에 설치하자.

> DataGrip은 유료이므로 무료를 원하면 mysql workbench를 설치하자.

먼저 [DataGrip 다운로드](https://www.jetbrains.com/ko-kr/datagrip/download/#section=mac) 사이트를 들어가서 다운받아보자.

다운 받은 후 실행하면 다음과 같은 화면이 나온다.

![](https://velog.velcdn.com/images/bini/post/49d489fa-7f38-41d6-a4dd-ecd637a3182c/image.png)

여기서 new project를 클릭 후 프로젝트 이름을 원하는 이름으로 입력후 ok를 누르면 다음과 같이 나온다.

![](https://velog.velcdn.com/images/bini/post/2c0574dc-5ceb-493c-93d0-5e9928a5a3ca/image.png)

## 2.5 Sample Database 설치

이제 실습을 위한 샘플 데이터를 설치해보자.

[샘플 데이터 베이스 다운로드](https://cafe.naver.com/thisisMySQL) 사이트를 들어가서 원하는 다운 링크를 클릭하여 압축파일을 받은 후 원하는 디렉터리에 압축을 풀어보자.

그런 후에 터미널을 켜서 압축을 푼 경로로 이동 후 mysql을 접속하자.

그런 후 아래와 같은 sql을 실행하자.

```sql
source employee.sql
```

그러면 설치가 진행될 것이다.

이제 제대로 설치가 되었는지 확인해보자.

아래와 같은 sql을 실행해보자.

```sql
show databases; -- 현재 데이테베이스 리스트를 보여주는 sql
```

그러면 아래와 같이 employees DB가 생긴것을 확인할 수 있다.

![](https://velog.velcdn.com/images/bini/post/2aaf856a-090c-44eb-9f75-a3512a632f5d/image.png)
