<p>능력평가 대비 SQL 다시보기.</p>
<hr />
<ol>
<li><p>DDL =craete, truncate, drop</p>
<pre><code class="language-java"> //CREATE
 create table student(
 컬럼명 varchar2(100) 제약조건,
 컬럼명1 Number 제약조건,
 Constraint 조건별명 Primary key(ID)
 Constraint 조건별명 Foreign key(내부컬럼) References 참조데이블(참조컬럼)
 )

 //DROP
 drop table student;
 drop database my250409;</code></pre>
</li>
<li><p>DML = select, insert, update, delete</p>
<pre><code class="language-java"> //SELECT
 select 컬럼명 from 테이블명 where 조건절

 //INSERT
 insert into 테이블명(컬럼명1, 컬럼명2) value ( 값1, 값2)

 //UPDATE
 update 테이블명 set 컬렴명1 = 값, 컬럼명2 = 값 where 조건절

 //DELETE
 delete from 테이블명 where 조건절</code></pre>
</li>
<li><p>TCL = commit, rollback, savepoint</p>
</li>
<li><p>트랜잭션의 특성 4가지</p>
<pre><code class="language-java"> -- 원자성(Atomicity)
 -- 일관성(Consistency)
 -- 고립성(Isolation)
 -- 영속성, 지속성(Durability)</code></pre>
</li>
<li><p>계정 생성 </p>
<pre><code class="language-java"> conn 아이디/비밀번호;

 grant  create user to 계정명;

 grand create session to 계정명;

 create user 계정명 identified by 비밀번호;

 alter user 계정명 identified by 비밀번호;

 alter user 계정명 default tablespace 테이블스페이스;

 alter user 계정명 temporary tablespace Temp;

 alter user 계정명 default tablespace 테이블스페이스 QUOTA unlimited on 계정명;</code></pre>
</li>
<li><p>테이블스페이스의 생성</p>
<pre><code class="language-java"> CREATE
     TABLESPACE 테이블스페이스명

     DATAFILE ‘ 경로와 이름’

     SIZE 크기

     AUTOEXTEND ON NEXT 크기

     (MAXSIZ 크기)</code></pre>
</li>
<li><p>join</p>
<pre><code class="language-java"> SELECT e.FIRST_NAME, e.DEPARTMENT_ID, d.DEPARTMENT_NAME
 FROM EMPLOYEES e (INNER)JOIN DEPARTMENTS d
 ON e.DEMARTMENT = d.DEPARTMENT</code></pre>
</li>
<li><p>view</p>
<pre><code class="language-java"> //뷰의 생성
 create or replace view 뷰이름 as(
     쿼리문
 )

 //뷰의 삭제
 drop view 뷰이름 (Restrict or Cascade)</code></pre>
</li>
</ol>