<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/fd1ca6d6-937d-4f65-9cde-896d90126b15/image.jpg" /></p>
<h1 id="database">Database</h1>
<hr />
<h2 id="dbdatabase">DB(DataBase)</h2>
<hr />
<p>구조화된 정보, 데이터의 조직화된 모음, 일반적으로 컴퓨터에 전자적으로 저장이되고 데이터 베이스 시스템에 의해 제어된다.</p>
<h2 id="dbmsdata-base-management-system">DBMS(Data Base Management System)</h2>
<hr />
<p>데이터베이스와 사용자 또는 프로그램 간의 매개체 역활을 하여 사용자가 정보의 구성,검색,수정,삭제와 같은 관리를 할 수 있게 해준다.</p>
<h3 id="종류">종류</h3>
<hr />
<ul>
<li>계층형 데이터베이스(HDBMS)</li>
<li>네트워크형 데이터베이스 NDBMS</li>
<li>관계형 데이터베이스 RDBMS</li>
<li>객체지향 데이터베이스(ODBMS)</li>
<li>NoSQL(Not Only SQL)</li>
</ul>
<hr />
<ul>
<li><p>노드 : 컴퓨터 네트워크 분야에서 사용되는 기초단위
  -단위이기 때문에 특정한것을 뜻하지는 않는다. 
  -보통은 네트워크에 연결되어 있는 제일 끝단 컴퓨터1개. 끝에있는거</p>
</li>
<li><p>결합도 : 서로 얼마나 결합이 잘되어있나, 그리고 의존성이 얼마나 높냐                   </p>
</li>
<li><p>응집도 : 높을수록 좋음. 하나의 파일에서 코드들이 의존성이 얼마나 높은가…</p>
</li>
</ul>
<p><br /><br /></p>
<h3 id="스키마">스키마</h3>
<hr />
<p>스키마는 데이터 사전에 저장되며, 다른 이름으로 메타데이터라고도 한다.</p>
<p>스키마는 시간에 따라 불변의 속성을 가진다.</p>
<p>개념스키마를 스키마라고 칭하기도 한다. → DB전체를 기술한것이기 때문에 한개 밖에 존재 못하기에.</p>
<ul>
<li><p>개념스키마 - 기업입장에서 본</p>
</li>
<li><p>내부스키마 - 물리적 저장</p>
</li>
<li><p>외부스키마 - 사용자 view</p>
</li>
</ul>
<p><br /><br /></p>
<h3 id="sqlstructured-query-language">SQL(Structured Query Language)</h3>
<hr />
<p>RDBM ⇒ 관계형 DBMS</p>
<h4 id="sql-문장의-종류">sql 문장의 종류</h4>
<hr />
<ul>
<li>DDL : 데이터베이스 객체를 생성, 삭제, 변경하는 언어<ul>
<li>create, drop, alter, truncate</li>
</ul>
</li>
<li>DML : 개발자 입장에서 제일 많이 사용하는 종류<ul>
<li>insert, update, delete, select</li>
</ul>
</li>
<li>DCL : 권한을 제어하는 언어<ul>
<li>grant, revoke</li>
</ul>
</li>
<li>TCL : 트랜잭션 제어어<ul>
<li>commit rollback, savepoint</li>
</ul>
</li>
</ul>
<p><br /><br /></p>
<h3 id="제약조건">제약조건</h3>
<hr />
<p>제약조건이란, 테이블에 문제가 되는 결함이 있는 데이터가 입력되지 않도록 미리 지정해둔 조건.</p>
<p>제약조건은 테이블을 생성할 때 함께 설정 할 수 있고, 추후에 생성하거나 변경 가능.</p>
<ul>
<li><p>NOT NULL 
데이터 비워두지 마라</p>
</li>
<li><p>UNIQE
중복되는 값을 허용하지 않는다
대신 비워두는건 가능하다</p>
</li>
<li><p>PRIMARY KEY(기본키)
UNIQUE + NOT NULL 테이블당 1개만 생성가능</p>
</li>
<li><p>FOREIGN KEY(외래키)
참조하는 테이블이 먼저 생성되어야 하며, 참조키가 참조 테이블의 기본키로 만들어져 있어야 한다.</p>
</li>
</ul>
<p><br /><br /></p>
<h4 id="테이블만들기">테이블만들기</h4>
<hr />
<p>DDL : CREATE에 대해 알아야함.</p>
<p>자료형 알아야함</p>
<p>제약조건 알아야함</p>
<p>테이블(행,열) 알아야함.</p>
<ul>
<li>테이블 생성하기<pre><code class="language-sql">CREATE TABLE TBL_MEMBER(
</code></pre>
</li>
</ul>
<p>--어떤 테이터를 저장하고 싶은지 명시</p>
<p>NAME VARCHAR2(20),</p>
<p>AGE NUMBER</p>
<p>);</p>
<pre><code>- 테이블 삭제
```sql
DROP TABLE TBL_MEMBER;</code></pre><ul>
<li>제약조건을 가지고 CAR 테이블 만들기</li>
<li>CONSTRAINT 제약조건명 제약조건종류(컬럼명)<pre><code class="language-sql">CREATE TABLE TBL_CAR(
</code></pre>
</li>
</ul>
<p>ID NUMBER,</p>
<p>BRAND VARCHAR(100),</p>
<p>COLOR VARCHAR(100),</p>
<p>PRICE NUMBER,</p>
<p>CONSTRAINT CAR_PK PRIMARY KEY(ID)</p>
<pre><code>    );


&lt;br&gt;&lt;br&gt;

### ALTER 문

---

테이블을 삭제하고 다시 만드는 방법도 있으나,

데이터가 이미 들어가 있을때 삭제하는 것은 거의 불가능하다.

ALTER TABLE이라는 명령어를 통해 테이블을 수정할 수 있다.
```sql
CREATE TABLE EX1(

COL1 VARCHAR2(10) NOT NULL,

COL2 VARCHAR2(10) NULL,

--DEFAULT SYSDATE = 데이터를 넣지 않을 시 현재 시간이 들어간다.

CREATE_DATE DATE DEFAULT SYSDATE

);</code></pre><ul>
<li><p>컬럼명 변경</p>
<pre><code class="language-sql">ALTER TABLE EX1 RENAME COLUMN COL1 TO COL11;</code></pre>
</li>
<li><p>컬럼 타입 변경</p>
<pre><code class="language-sql">ALTER TABLE EX1 MODIFY COL2 VARCHAR2(30);</code></pre>
</li>
<li><p>컬럼 추가</p>
<pre><code class="language-sql">ALTER TABLE EX1 ADD COL3 NUMBER;</code></pre>
</li>
<li><p>이미 생성된 테이블에 제약조건 추가하기</p>
</li>
</ul>
<blockquote>
<p>ALTER 테이블명 ADD CONSTRAINT 제약조건명 제약조건종류(컬럼명)</p>
</blockquote>
<pre><code class="language-sql">ALTER TABLE EX1 ADD CONSTRAINT PK_EX1 PRIMARY KEY(COL11);</code></pre>
<p><br /><br /></p>
<h4 id="제약조건-삭제하기">제약조건 삭제하기</h4>
<hr />
<blockquote>
<p>ALTER TABLE 테이블명 DROP CONSTAINT 제약조건명;</p>
</blockquote>
<p>ex)</p>
<pre><code class="language-sql">ALTER TABLE EX1 DROP CONSTRAINT PK_EX1;</code></pre>
<hr />
<p>ex) 학생 테이블 DEFAULT, CHECK 제약조건을 사용</p>
<blockquote>
<p>CONSTRAINT 제약조건이름 제약조건 OR CHECK 조건</p>
</blockquote>
<pre><code class="language-sql">CREATE TABLE TBL_STUDENT(

  ID NUMBER,

  NAME VARCHAR2(100),

  MAJOR VARCHAR2(100),

  GENDER CHAR(1) DEFAULT 'W' NOT NULL

  CONSTRAINT BAN_CHAR CHECK(GENDER='M' OR GENDER='W'),

  BIRTH DATE CONSTRAINT BAN_DATE CHECK(BIRTH &gt;= TO_DATE('1980-01-01','YYYY-MM-DD')),

  CONSTRAINT STD_PK PRIMARY KEY(ID)

);</code></pre>