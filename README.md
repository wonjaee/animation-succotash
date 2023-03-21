# ORACLE-Exercise
### 오라클XE 다운로드 https://www.oracle.com/database/technologies/xe-downloads.html
### 바커표기법/IE표기법  https://dataonair.or.kr/db-tech-reference/d-guide/da-guide/?pageid=2&mod=document&keyword=%EB%8D%B0%EC%9D%B4%ED%84%B0+%EB%AA%A8%EB%8D%B8%EB%A7%81&uid=278
### draw.io  https://app.diagrams.net/

***

***
### 오라클 튜토리얼  https://www.oracletutorial.com/
### 샘플 스키마 다운로드  https://github.com/oracle-samples/db-sample-schemas/releases

# 1. human_resources 폴더를 복사하여 XE인스턴스의 경로에 복사하기
- C:\app\Administrator\product\21c\dbhomeXE\demo\schema 경로에 폴더 복사하여 넣으세요
# 2. main.sql 파일을 메모장으로 열어서 제일아래부분쪽 경로수정 @__SUB__CWD__/human_resources/파일명
@__SUB__CWD__ --> @?/demo/schema
```
@?/demo/schema/human_resources/hr_cre
-- 
-- populate tables
--
@?/demo/schema/human_resources/hr_popul
--
-- create indexes
--
@?/demo/schema/human_resources/hr_idx
--
-- create procedural objects
--
@?/demo/schema/human_resources/hr_code
--
-- add comments to tables and columns
--
@?/demo/schema/human_resources/hr_comnt
--
-- gather schema statistics
--
@?/demo/schema/human_resources/hr_analz
```

```
SQL*Plus: Release 21.0.0.0.0 - Production on 수 3월 8 10:36:58 2023
Version 21.3.0.0.0

Copyright (c) 1982, 2021, Oracle.  All rights reserved.

사용자명 입력: sys as sysdba
비밀번호 입력:

다음에 접속됨:
Oracle Database 21c Express Edition Release 21.0.0.0.0 - Production
Version 21.3.0.0.0

SQL> alter session set "_ORACLE_SCRIPT"=true;

세션이 변경되었습니다.

SQL> @?/demo/schema/human_resources/hr_main.sql

specify password for HR as parameter 1:
1의 값을 입력하십시오: hr

specify default tablespeace for HR as parameter 2:
2의 값을 입력하십시오: users

specify temporary tablespace for HR as parameter 3:
3의 값을 입력하십시오: temp

specify password for SYS as parameter 4:
4의 값을 입력하십시오: oracle

specify log path as parameter 5:
5의 값을 입력하십시오: C:\app\Administrator\product\21c\dbhomeXE\demo\schema\log\

specify connect string as parameter 6:
6의 값을 입력하십시오: localhost:1521/xe

```
***
***
#### ORACLE XE 설치후 접속
#### SYS 또는 SYSTEM 계정으로 접속 USER 생성
-- SYSDBA 롤(ROLE)로 접속
사용자 : SYS AS SYSDBA
비밀번호: 
---
# 10g,11g - 그리드
# 12c ~ 21c - 클라우드 컴퓨팅
- 클라우드에서 사용자 생성시 common_user_prefix --> c##
- create user c##아이디 identified by 비밀번호;
- c## 없이 생성하려면?
- alter session set "_ORACLE_SCRIPT"=true;
- 세션 변경후 사용가능

-- 사용자 생성
```
SQL > CREATE USER 아이디 IDENTIFIED BY 비밀번호;
```
-- 사용자 삭제
```
SQL > DROP USER 아이디;
```
***
## DDL
- 테이블 생성
```
CREATE TABLE table_name(
   column1 datatype,
   column2 datatype,
   column3 datatype,
   .....
   columnN datatype,
   PRIMARY KEY( one or more columns )
);
```
- 테이블 삭제
```
DROP TABLE table_name;
```
- 테이블 수정
```
ALTER TABLE table_name ADD column_name datatype;
ALTER TABLE table_name DROP COLUMN column_name;
ALTER TABLE table_name MODIFY COLUMN column_name datatype;
ALTER TABLE table_name MODIFY column_name datatype NOT NULL;
```
