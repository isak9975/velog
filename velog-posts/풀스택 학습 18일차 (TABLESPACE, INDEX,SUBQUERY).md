<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/dc9b1549-bffb-4ed4-8cd8-2114b6176a11/image.jpg" /></p>
<h1 id="테이블스페이스-tablespace">테이블스페이스 (tablespace)</h1>
<hr />
<p><strong>논리적 저장소 단위.</strong></p>
<p>데이터베이스 객체(테이블,인덱스 등) 의 데이터를</p>
<p>저장하는 컨테이너 역활을 하며, 실제 데이터는 </p>
<p>하나 이상의 데이터 파일에 저장된다.</p>
<p>테이블스페이스는 하나 이상의 데이터 파일로 구성이 되고, </p>
<p>이 파일들은 물리적 저장소에 위치하며 실제 데이터를 저장한다.</p>
<ul>
<li><p>tablespace_name
테이블스페이스의 이름을 확인할 수 있다.</p>
</li>
<li><p>status 
테이블스페이스의 현재 상태를 나타낸다.</p>
</li>
<li><p>contents
테이블스페이스에 저장되는 데이터의 종류를 표시</p>
</li>
</ul>
<pre><code class="language-sql">conn sys as sysdba

select file_name, tablespcae_name,autoextensible from dba_data_files;

dba_data_files</code></pre>
<p>오라클에서 사용되는 데이터 파일들의 세부정보를 제공하는 뷰</p>
<ul>
<li><p>file_name
데이터 파일의 전체 경로와 파일명을 나타낸다.
실제 디스크 상에 존재하는 파일의 위치를 확인할 수 있다.</p>
</li>
<li><p>tablespace_name
해당 데이터 파일이 소속된 테이블 스페이스의 이름을 보여준다.
이를 통해 논리적 저장 단위와 물리적 파일 간의 관계를 파악할 수 있다.</p>
</li>
<li><p>autoextensible
데이터 파일이 자동 확장(autoextend) 기능으로 설정되어 있는지 여부를 나타낸다.
‘yes’ 또는 ‘no’ 로 표기되며, ‘yes’인 경우 파일 크기가 설정된 조건에 따라 자동으로 늘어난다.
<br /><br /></p>
</li>
</ul>
<h2 id="테이블-스페이스-생성">테이블 스페이스 생성</h2>
<hr />
<pre><code class="language-sql">CREATE

TABLESPACE 테이블스페이스명

DATAFILE ‘ 경로와 이름’

SIZE 크기

AUTOEXTEND ON NEXT 크기

(MAXSIZ 크기)</code></pre>
<p><br /><br /></p>
<h3 id="권한의-종류">권한의 종류</h3>
<hr />
<h4 id="1-시스템-권한">1. 시스템 권한</h4>
<ul>
<li><p>데이터 베이스 전체에 영향을 미치는 작업</p>
<p> ( 사용자의 생성, 데이터베이스 구조 변경)</p>
</li>
<li><p>CREATE SESSION : 데이터 베이스에 접속할 수 있는 권한</p>
</li>
<li><p>CREATE TABLE : 테이블을 생성할 수 있는 권한</p>
</li>
<li><p>ALTER SYSTEM : 시스템 설정을 변경할 수 있는 권한</p>
</li>
<li><p>CREATE USER : 사용자 계정을 생성할 수 있는 권한</p>
</li>
</ul>
<h4 id="2-객체-권한">2. 객체 권한</h4>
<ul>
<li>특정 데이터베이스 객체( 테이블, 뷰{가상의 테이블}, 프로시저{함수(사용자가 정의)} )에 부여되는 권한</li>
</ul>
<h5 id="2-1-권한-종류">2-1. 권한 종류</h5>
<ul>
<li><p>SELECT</p>
</li>
<li><p>INSERT</p>
</li>
<li><p>UPDATE</p>
</li>
<li><p>DELETE</p>
<blockquote>
</blockquote>
<p>GRANT SELECT, INSERT, UPDATE ON 테이블 TO 대상</p>
</li>
</ul>
<h4 id="3-역활">3. 역활</h4>
<ul>
<li><p>한 번에 여러 권한을 사용자에게 부여하거나 회수 할수 있도록 돕는다.</p>
</li>
<li><p>CONNECT : 기본적인 데이터베이스 접속 권한을 제공하는 역활</p>
</li>
<li><p>RESOURCE : 테이블, 인덱스 등 객체를 생성할 수 있는 권한을 포함하는 역활</p>
</li>
<li><p>DBA : 데이터베이스의 모든 관리 권한을 포함하는 최고 수준의 역활</p>
<blockquote>
</blockquote>
<p>GRANT CREATE USER TO 대상;</p>
<pre><code class="language-sql">//SCOTT에게 계정 생성 권한 주기
GRANT CREATE USER TO SCOTT;
</code></pre>
</li>
</ul>
<p>CONN SCOTT/tiger</p>
<p>CREATE USER BABY IDENTIFIED BY BABY;</p>
<p>CONN BABY</p>
<p>ERROR</p>
<p>CONN SYSTEM/1234</p>
<p>//데이터 베이스에 접속할 권한</p>
<p>GRANT CREATE SESSION TO BABY;</p>
<p>//테이블 만들기 권한</p>
<p>GRANT CREATE TABLE TO BABY;</p>
<p>//쓰기 권한의 용량 + 기본테이블스페이스</p>
<p>ALTER USER 계정명 DEFAULT TABLESPACE 테이블스페이스명 QUOTA UNLIMITED ON BABY;</p>
<p>//임시 저장공간</p>
<p>ALTER USER BABY TEMPORARY TABLESPACE TEMP;</p>
<p>//줘야할 권한이 많네</p>
<p>SQL&gt; CREATE TABLE TEST001(
2  ID VARCHAR2(10),
3  PW VARCHAR2(10),
4  AGE NUMBER,
5  CONSTRAINT BABY_PK PRIMARY KEY(ID));</p>
<p>//드디어 테이블 만들기 성공.</p>
<pre><code>#### 4. 권한 회수
권한을 주거나 뺏는것은 관리자 계정으로부터 해야한다.
```sql
//BABY 계정의 기본 테이블스페이스를 BABY로 지정하면서
//무제한으로 사용 사용할것이다.

ALTER USER BABY DEFAULT TABLESPACE BABY QUOTA UNLIMITED ON BABY;</code></pre><pre><code>- QUOTA
사용자가 특정 테이블스페이스 내에서 사용할 수 있는 디스크 공간의 최대향을 지정하는데 사용되는 키워드</code></pre><p><br /><br /></p>
<h2 id="index">INDEX</h2>
<hr />
<p>원하는 레코드(행)을 빠르게 찾아갈 수 있도록 만들어진 데이터 구조</p>
<p>저장소처럼 색인을 통해 찾아가는것을 INDEX라고 한다.</p>
<p><br /><br /></p>
<h4 id="b-tree">B-TREE</h4>
<hr />
<p>제목의 순서에 따라 책들을 정리해놓고 해당되는 위치를 찾아가는 것.</p>
<ul>
<li><p>인덱스(INDEX)</p>
<ul>
<li>테이블에 저장된 데이터를 보다 빠르게 검색할 수 있또록 도와주는 자료구조</li>
</ul>
</li>
<li><p>장점</p>
<ul>
<li><p>빠른 검색 : 인덱스를 사용하면 테이블 전체를 검색하지 않아도 되므로, 데이터 검색 속도가 크게 향상된다</p>
</li>
<li><p>효율적인 정렬 : 이미 정렬된 형태로 인덱스가 저장되어 있어, 정렬 연산이 빠르게 수행된다.</p>
</li>
</ul>
</li>
<li><p>단점</p>
<ul>
<li>추가 저장공간 필요; 인뎃그에르 생서ㅇ하면 별도의 저장 공간이 파료앟다.</li>
</ul>
</li>
</ul>
<p>데이터 수정 미용 증가 : INSPERT, UPDATE, DELETE 자업시 인덱스도 함께 갱신이 되어야ㅏ 하므로 성능이 허 라 저하될 수 있다</p>
<p><br /><br /></p>
<h4 id="언제-인덱스가-사용이-되는가">언제 인덱스가 사용이 되는가?</h4>
<hr />
<ul>
<li><p>WHERE 절</p>
<p>쿼리에서 특정 조건을 만족하는 행을 찾을때, 조건에 사용된 컬럼에 읺덱스가 있으면 DBOS가 전체 테이블을 스캔하는 대신 엑덱스를 통해 빠르게 해당 행의 위치를 찾아간다.</p>
</li>
<li><p>GROUP BY, ORDER BY</p>
</li>
<li><p>결과를 정렬 또는 그룹화 할 때도 인덱스가 사용된다.</p>
<br />
#### INDEX의 삭제
</li>
</ul>
<hr />
<ul>
<li><p>조회 성능을 높이기 위해 만든 객체지만 저장공간을 많이 차지하며 DDL작업(INSERT, UPDATE, DELETE)시 부하가 많이 발생해 전체적인 데이터베이스 성능을 저하시킨다</p>
</li>
<li><p>DBA는 주기적으로 INDEX를 검토하여 사용하지 않는 인덱스는 삭제하는 것이 데이터베이스 전체 성능을 향상 시킬 수 있다.</p>
</li>
</ul>
<blockquote>
</blockquote>
<p>DROP INDEX 인덱스명;
<br /></p>
<h4 id="index를-rebuild하기">INDEX를 REBUILD하기</h4>
<hr />
<ul>
<li>INSERT, UPDATE, DELETE와 같은 작업이 발생하면 인덱스의 검색 속도를 정하시키고 전체 데이터베이스 성능에 영향을 미치므로 주기적으로 INDEX를 리빌딩하는 작업을 해줘야 한다.<blockquote>
</blockquote>
ALTER INDEX 인덱스명 REBUILD;</li>
</ul>
<p><br /><br /></p>
<h3 id="explain-plan">EXPLAIN PLAN</h3>
<hr />
<p>자동으로 만들어진 INDEX던, 우리가 수동으로 만든 INDEX건 조회할 때 사용이 되는거라면
잘 사용이 되고 있는지 확인을 해야할 필요가 있다.
<br /></p>
<h4 id="index-조회하는-법">Index 조회하는 법</h4>
<blockquote>
</blockquote>
<p>EXPLAIN PLAN FOR + SQL문</p>
<ul>
<li>ORACLE 데이터베이스에서 SQL 쿼리가 실행될 때</li>
<li>어떤 경로로 수행되는지를 미리 확인할 수 있는 명령어<br />
#### 주요개념</li>
<li>실행 계획(EXPLAIN PLAN)<ul>
<li>SQL 쿼리를 처리하기 위한 단계별 작업 순서를 나타낸다.</li>
<li>테이블 스캔, 인덱스 스캔, 조인 방식이 포함된다.</li>
</ul>
</li>
<li>실제로 쿼리를 실행하지는 않고, 쿼리의 실행 경로를 분석
   -실행 계획을 통해 쿼리 성능 개선, 인덱스 활용 여부 병목 현상 등을 진달할 수 있다.</li>
<li>PLAN_TABLE</li>
<li>실행 계획 정보는 기본적으로 PLAN_TABLE 이라는 테이블에 저장된다.</li>
<li>이후 DBMS_XPLAN.DISPLAY함수를 이용하여 보기 쉽게 출력할 수 있다.</li>
<li>데이터가 많은 곳에서 사용하는게 좋다 + 인덱스 정리하기 위해서 사용한다(사용별로 없으면 INDEX많은면 안좋으니 삭제하기 위함.)</li>
</ul>
<p><code>EXPLAIN PLAN **FOR**</code></p>
<blockquote>
</blockquote>
<p><strong>`SELECT</strong> * <strong>FROM</strong> EMPLOYEES <strong>WHERE</strong> LAST_NAME='Smith';`</p>
<p><code>-PLAN 테이블에 이 데이터가 어떻게 실행되는지 담긴다</code></p>
<blockquote>
</blockquote>
<p><strong>`SELECT</strong> * <strong>FROM</strong> <strong>TABLE</strong>(DBMS_XPLAN.DISPLAY); --==&gt; 인덱스 사용여부 확인`</p>
<p><br /><br /></p>
<h3 id="서브쿼리subquery">서브쿼리(SUBQUERY)</h3>
<hr />
<p>특정 sql문장 안에 또 다른 sql문장이 들어가는 것.</p>
<ul>
<li><p>FROM절( IN LINE VIEW ) : 쿼리문으로 출력되는 결과를 테이블처럼 사용하겠다.</p>
</li>
<li><p>SELECT절( SCALAR ) : 하나의 컬럼처럼 사용되는 서브 쿼리</p>
</li>
<li><p>WHERE절( SUB QUERY ) : 하나의 변수처럼 사용한다.</p>
</li>
<li><p>단일행 서브쿼리 : 쿼리 결과가 단일행만 반환하는 서브쿼리</p>
</li>
<li><p>다중행 서브쿼리 : 쿼리 결과가 다중행을 리턴하는 서브쿼리</p>
</li>
<li><p>다중 컬럼 서브쿼리 : 쿼리 결과가 다중컬럼을 반환하는 서브쿼리</p>
</li>
<li><p>CONCATNATION(연결) : || =&gt; 2개 이상 가능.</p>
</li>
<li><p>사원테이블에서 사원들의 이름 연결하기</p>
<blockquote>
</blockquote>
</li>
<li><p><em>SELECT*</em> FIRST_NAME || ' ' || LAST_NAME <strong>FROM</strong> EMPLOYEES;</p>
</li>
<li><p>00의 급여는 00 이다</p>
<blockquote>
</blockquote>
</li>
<li><p><em>SELECT*</em> FIRST_NAME || '의 급여는 '|| SALARY ||'이다'</p>
</li>
</ul>
<p><br /><br /></p>
<h3 id="별칭alias">별칭(alias)</h3>
<hr />
<ul>
<li><p>SELECT절
컬럼명 뒤에 한칸 띄우고 작성</p>
<ul>
<li>FROM 절
테이블명 뒤에 한칸 띄우고 작성</li>
</ul>
</li>
</ul>
<h4 id="별칭의-특징">별칭의 특징</h4>
<p> 테이블에 별칭을 줘서 컬럼을 단순, 명확히 할 수 있다.</p>
<ul>
<li>현재의 SELECT 문장에서만 유효하다.</li>
<li>테이블 별칭은 길이가 30자까지 가능하나 짧을수록 좋다.</li>
<li>FROM절에 테이블 별칭 설정시 해당 테이블 별칭은</li>
<li>SELECT문장에서 테이블 이름 대신 사용할 수 있다.</li>
</ul>
<pre><code class="language-sql">SELECT 
    COUNT(SALARY) AS 개수,
    MAX(SALARY) AS 최대값, 
    MIN(SALARY) AS 최소값,
    SUM(SALARY) AS 합계,
    AVG(SALARY) AS 평균값
FROM EMPLOYEES;</code></pre>
<ul>
<li>두개 이상의 테이블에서 각각의 컬럼을 조회하려고 할때</li>
<li>어떤 테이블에서 온 컬럼인지 확실하게 해야할 때가 있다.<blockquote>
</blockquote>
</li>
<li><em>SELECT**  *E</em>.DEPARTMENT_ID, <em>D</em>.DEPARTMENT_ID</li>
<li><em>FROM** EMPLOYEES *e</em>, DEPARTMENTS <em>d</em> ;</li>
</ul>
<p><br /><br /></p>
<h3 id="오라클조인-vs-ansi조인표준">오라클조인 VS ANSI조인(표준)</h3>
<hr />
<ul>
<li><p>ANSI JOIN</p>
<blockquote>
</blockquote>
<p>FROM 테이블명A JOIN 테이블명B 
ON 테이블A.조인컬럼 = 테이블B.조인컬럼</p>
</li>
<li><p>2개 조인</p>
</li>
</ul>
<pre><code class="language-sql">-- 사원테이블과, JOBS 테이블을 이용하여
-- 이름, 성, 직종번호, 직종 이름을 조회하세요
SELECT 
    E.FIRST_NAME, 
    E.LAST_NAME,
    J.JOB_TITLE 
FROM EMPLOYEES e JOIN JOBS j ON E.JOB_ID = J.JOB_ID;</code></pre>
<ul>
<li>3개 조인</li>
</ul>
<pre><code class="language-sql">-- 사원, 부서, 지역테이블로부터
-- 이름, 이메일, 부서번호, 부서명, 지역번호, 도시명
-- 을 조회하되, 도시가 'Seattle'인 경우만 조회하기
SELECT 
    e.FIRST_NAME,
    e.EMAIL,
    e.DEPARTMENT_Id,
    d.DEPARTMENT_NAME,
    d.LOCATION_ID,
    l.city
FROM EMPLOYEES e JOIN DEPARTMENTS d ON e.DEPARTMENT_ID = d.DEPARTMENT_Id
JOIN LOCATIONS l ON d.LOCATION_ID =l.LOCATION_ID;</code></pre>
<p><br /><br /></p>
<h3 id="self-join">self join</h3>
<hr />
<ul>
<li>1-1 self inner join
나의 테이블 내에서 다른 컬럼을 찹조하기 위해 사용하는
자기 자신과의 조인 방법이다.
이를 통해 데이터베이스의에서 한 테이블 내의 값을 다른 값과 연결 할 수 있다.</li>
</ul>
<blockquote>
</blockquote>
<p>select a.컬럼1, b.컬럼1
from 테이블A a
join 테이블A b
on a.열 = b.열;</p>