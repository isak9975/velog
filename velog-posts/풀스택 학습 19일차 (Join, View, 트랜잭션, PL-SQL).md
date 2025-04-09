<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/e5bb7d4b-2ced-4413-9e59-602be5a424b7/image.jpg" /></p>
<h2 id="join">Join</h2>
<hr />
<h3 id="on과-where의-차이">ON과 WHERE의 차이</h3>
<hr />
<p>ON : 조인시 두 테이블의 행의 결합 조건을 지정</p>
<p>특히 외부 조인에서는 어떤 행을 결합할지 결정하는 중요한 역할을 한다.</p>
<p>WHERE : 결합된 결과 집합에 대해 추가적인 필터링을 적용한다.</p>
<p><br /><br /></p>
<h3 id="cross-inner-join">CROSS INNER JOIN</h3>
<hr />
<p>두 개 이상의 테이블에서  ‘모든 가능한 조합’’을 만ㄷ르어 결과를 반환하는 조인방법</p>
<p>이를 통해 두개 이상의 테이블을 조합하여 새로운 테이블을 만들 수 있다</p>
<p>두 테이블이 서로 관련이 없어도 조인이 가능하다
<br /><br /></p>
<h3 id="outer-join">OUTER JOIN</h3>
<hr />
<ul>
<li>두 테이블에서 '공통된 값을 가지지 않는 행들'도 반환한다.
<br /><br /><h3 id="left-outer-join">LEFT OUTER JOIN</h3>
</li>
</ul>
<hr />
<ul>
<li><p>'왼쪽 테이블의 모든 행'과 '오른쪽 테이블과 왼쪽 테이블이 공통적으로 가지는 값을 반환한다.'</p>
</li>
<li><p>교집합과 차집합의 연산 결과를 합친것과 같다.</p>
</li>
<li><p>만약에 오른쪽 테이블에서 공통도니 값을 가지고 있는 행이 없다면 NULL을 반환</p>
</li>
<li><p>사원테이블과 부서 테이블의 LEFT OUTER JOIN을 이요하여</p>
</li>
<li><p>사원이 어느부서에 있는지 조회하기</p>
<blockquote>
</blockquote>
</li>
<li><p><em>SELECT** *E</em>.FIRST_NAME,  <em>D</em>.DEPARTMENT_NAME</p>
</li>
<li><p><em>FROM** EMPLOYEES *e</em></p>
</li>
<li><p><em>LEFT** <strong>OUTER</strong> <strong>JOIN</strong> DEPARTMENTS *d</em></p>
</li>
<li><p><em>ON** *E</em>.DEPARTMENT_ID = <em>D</em>.DEPARTMENT_ID;</p>
</li>
<li><p>RIGHT OUTER JOIN</p>
</li>
<li><p>LEFT OUTER JOIN의 반대</p>
</li>
<li><p>공통데이터와 오른ㅉ고 테이블에 있는 데이터를 조회</p>
<blockquote>
</blockquote>
</li>
<li><p><em>SELECT** * <strong>FROM</strong> STADIUM *s</em></p>
</li>
<li><p><em>RIGHT** <strong>OUTER</strong> <strong>JOIN</strong> TEAM *t</em></p>
</li>
<li><p><em>ON** *S</em>.HOMETEAM_ID = <em>T</em>.TEAM_ID;</p>
</li>
<li><p>LEFT와 RIGHT중에 뭘 많이 쓸까?</p>
</li>
<li><p>상황에 따라 다르다...</p>
</li>
<li><p>대부분 왼쪽 테이블의 데이터를 중심으로 분석하고자 하는 경우가</p>
</li>
<li><p>많기 때문에 LEFT를 더 많이 사용하는것 같다.</p>
</li>
<li><p>FULL OUTER JOIN</p>
</li>
<li><p>두 테이블에서 '모든값'을 반환한다.</p>
</li>
<li><p>서로 공통되지 않은 부분은 NULL로 채운다</p>
</li>
<li><p>합집합의 연산과 같다.</p>
<blockquote>
</blockquote>
</li>
<li><p><em>SELECT** *E</em>.FIRST_NAME, <em>D</em>.DEPARTMENT_NAME <strong>FROM</strong> EMPLOYEES <em>E</em></p>
</li>
<li><p><em>FULL** <strong>OUTER</strong> <strong>JOIN</strong> DEPARTMENTS *d</em></p>
</li>
<li><p><em>ON** *E</em>.DEPARTMENT_ID = <em>D</em>.DEPARTMENT_ID;</p>
</li>
</ul>
<p><br /><br /></p>
<h3 id="비등가조인">비등가조인</h3>
<hr />
<ul>
<li>두 테이블을 결합할 때 부등호(&gt;,&lt;,&lt;=,&gt;=),BTWEEN, LIKE 등</li>
<li>다양한 비고 연산자를 통해 조인 조건을 지정하는 방식</li>
<li>특정 값이 일정 범위 내에 속하거나, 두 값 사이의 관계를</li>
<li>비교하여 행을 결핣할 때 유용하다.<blockquote>
</blockquote>
</li>
<li><em>SELECT** *E</em>.EMPNO, <em>E</em>.ENAME, <em>S</em>.GRADE, <em>E</em>.SAL</li>
<li><em>FROM** SALGRADE *s</em>  <strong>JOIN</strong> EMP <em>E</em></li>
<li><em>ON** *E</em>.SAL <strong>BETWEEN</strong> <em>S</em>.LOSAL <strong>AND</strong> <em>S</em>.HISAL;</li>
</ul>
<p><br /><br /></p>
<h3 id="using">USING</h3>
<hr />
<ul>
<li><p>USING() : 중복되는 컬럼이 생길 시 맨 앞으로 출력하며</p>
</li>
<li><p>중복 컬럼을 한개만 출력한다.</p>
<blockquote>
</blockquote>
</li>
<li><p><em>SELECT*</em> * <strong>FROM</strong> EMP <strong>JOIN</strong> DEPT</p>
</li>
<li><p><em>USING*</em>(DEPTNO);</p>
</li>
<li><p>ON EMP.DEPTNO = DEPT.DEPTNO; 대신에 USING(DEPTNO); 사용</p>
</li>
</ul>
<h3 id="natural-join">NATURAL JOIN</h3>
<hr />
<ul>
<li><p>두 테이블 간의 동일한 이름을 갖는 모든 컬럼들에 대해</p>
</li>
<li><p>등가 조인을 수행한다</p>
</li>
<li><p>컬럼 이름 뿐만 아니라 타입도 같아야 한다.</p>
<blockquote>
</blockquote>
</li>
<li><p><em>SELECT** * <strong>FROM</strong> EMP <strong>INNER</strong> <strong>JOIN</strong> DEPT *d</em></p>
</li>
<li><p><em>ON** EMP.DEPTNO = *D</em>.DEPTNO;</p>
</li>
<li><p><em>SELECT** * <strong>FROM</strong> EMP <strong>NATURAL</strong> <strong>JOIN</strong> DEPT *D</em>;</p>
</li>
<li><p>자동매칭</p>
</li>
<li><p>두 테이블에서 이름이 동일한 컬럼을 찾아서, 해당 컬럼들이 값이 일치하는 행끼리</p>
</li>
<li><p>자동으로 결합한다.</p>
</li>
<li><p>중복컬럼제거</p>
</li>
<li><p>조인 결과에서 공통 컬럼은 한 번만 표시된다.</p>
</li>
<li><p>명시적 조건 생략</p>
</li>
<li><p>ON절이나 USING절 없이 간단한게 조인할 수 있다.</p>
</li>
<li><p>의도하지 않은 결과가 나올 수 있다.</p>
</li>
<li><p>자동으로 공통컬럼을 기준으로 조인하기 때문에, 개발자가 어떤 컬럼을</p>
</li>
<li><p>어떤 기준으로 조인하는지 명확히 알기 어려울 수 있다.</p>
</li>
</ul>
<p><br /><br /></p>
<h3 id="union">UNION</h3>
<hr />
<ol>
<li>UNION</li>
</ol>
<ul>
<li>두 개의 테이블에서 '중복을 제거하고 합친 모든행'을 반환.</li>
</ul>
<blockquote>
</blockquote>
<p><strong>SELECT</strong> <em>E</em>.FIRST_NAME <strong>FROM</strong> EMPLOYEES <em>e</em>
<strong>UNION</strong>
<strong>SELECT</strong> <em>D</em>.DEPARTMENT_NAME <strong>FROM</strong> DEPARTMENTS <em>d</em> ; --하나의 행으로 합쳐짐</p>
<ol start="2">
<li>UNION ALL</li>
</ol>
<ul>
<li>중복을 제거하지 않고 모두 합친 행을 반환<blockquote>
</blockquote>
</li>
<li><em>SELECT** *E</em>.FIRST_NAME <strong>FROM</strong> EMPLOYEES <em>e</em></li>
<li><em>UNION*</em> <strong>ALL</strong></li>
<li><em>SELECT** *D</em>.DEPARTMENT_NAME <strong>FROM</strong> DEPARTMENTS <em>d</em>  <strong>ORDER</strong> <strong>BY</strong> FIRST_NAME; --중복있는 하나의 행 합치기</li>
</ul>
<p><br /><br /></p>
<h3 id="view">VIEW</h3>
<hr />
<ul>
<li>하나 이상의 테이블이나 다른 뷰의 데이터를 볼 수 있게 해주는</li>
<li>데이터베이스 객체이다.</li>
<li>쿼리문을 작성하면 -&gt; 1회성</li>
<li>쿼리 결과를 마치 하나의 테이블처럼 사용할 수 있도록 하는 가상 테이블</li>
<li>실제 데이터는 저장하지 않고, 뷰를 찹조할 때마다 미리 정의된</li>
<li>쿼리문이 실행되어 결과가 생성된다.</li>
<li>테이블 뿐만 아니라 다른 뷰를 참조해 새로운 뷰를 만들 수도 있다.</li>
<li>사용목적</li>
<li>여러 테이블에서 필요한 정보를 사용할때가 많다.</li>
<li>VIEW에 저장하면 간단하게 호출할 수 있다.</li>
</ul>
<h3 id="view의-특징">VIEW의 특징</h3>
<hr />
<ul>
<li>독립성</li>
<li>테이블 구조가 변경되어도 뷰를 사용하는 응용프로그램은 변경하지 않아도 된다.</li>
<li>편리성</li>
<li>복잡한 쿼리문을 뷰로 생성함으로써 관련 쿼리를 단순하게 작성할 수 있다.</li>
<li>자주 사용하는 SQL문이면 뷰에 저장하고 편리하게 사용할 수 있다.</li>
<li>보안성</li>
<li>숨기고 싶은 정보가 존재한다면, 뷰를 생성할 때 해당 컬럼은 빼고</li>
<li>생성함으로써 사용자에게 정보를 감출 수 있다</li>
<li>VIEW의 생성</li>
<li>OR REPLACE 옵션은 기존의 정의를 변경하는데 사용할 수 있다.</li>
</ul>
<p><br /><br /></p>
<h3 id="view-생성하는법">VIEW 생성하는법</h3>
<hr />
<blockquote>
</blockquote>
<p>CREATE OR REPLACE VIEW 뷰이름 AS(
쿼리문
)</p>
<p><br /><br /></p>
<h3 id="veiw의-삭제">VEIW의 삭제</h3>
<hr />
<ul>
<li><p>DROP VIEW 뷰이름 [RESTRICT or CASCADE]</p>
</li>
<li><p>RESTRICT : 뷰를 다른곳에서 참조하고 있다면 삭제가 취소</p>
</li>
<li><p>CASCADE : 뷰를 참조하는 다른 뷰나 제약 조건까지 모두 삭제된다.</p>
<blockquote>
</blockquote>
</li>
<li><p><em>SELECT** * <strong>FROM</strong> PLAYER *p</em>;</p>
</li>
<li><p>선수의 이름과 나이를 조회하세요</p>
</li>
<li><p>EX) 홍길동 35</p>
<blockquote>
</blockquote>
</li>
<li><p><em>SELECT** *P</em>.PLAYER_NAME, <strong>ROUND</strong>((SYSDATE-<em>P</em>.BIRTH_DATE)/365) <em>AGE</em> <strong>FROM</strong> PLAYER <em>p</em>;</p>
</li>
<li><p><em>DROP*</em> <strong>VIEW</strong> PLAYER_AGE;</p>
</li>
<li><p>PLAYER_AGE라는 뷰를 만들어서 저장</p>
<blockquote>
</blockquote>
</li>
<li><p><em>CREATE*</em> <strong>OR</strong> <strong>REPLACE</strong> <strong>VIEW</strong> PLAYER_AGE <strong>AS</strong>(</p>
</li>
<li><p><em>SELECT** <strong>ROUND</strong>((<strong>SYSDATE</strong>-P.BIRTH_DATE)/365)AGE, P.</em></p>
</li>
<li><p><em>FROM*</em> PLAYER p
);</p>
<blockquote>
</blockquote>
</li>
<li><p><em>SELECT** * <strong>FROM</strong> PLAYER_AGE *pa</em>;</p>
</li>
</ul>
<p>--30살이 넘은 선수를 조회</p>
<blockquote>
<p><strong>SELECT</strong> * <strong>FROM</strong> PLAYER_AGE <em>pa</em> <strong>WHERE</strong> AGE &gt; 30;</p>
</blockquote>
<p><br /><br /></p>
<h3 id="tcl-transaction-controller-language-">TCL( Transaction Controller Language )</h3>
<hr />
<ul>
<li>트랜젝션 : 데이터베이스의 작업을 처리하는 논리적 연산 단위</li>
<li>select , insert, update, delete문을 하나의 작업단위라고 한다.</li>
</ul>
<h3 id="트랜젝션의-특성">트랜젝션의 특성</h3>
<hr />
<ul>
<li>원자성(Atomicity)</li>
<li>일관성(Consistency)</li>
<li>고립성(Isolation)</li>
<li>영속성, 지속성(Durability)</li>
</ul>
<h3 id="tcl의-종류">TCL의 종류</h3>
<hr />
<ul>
<li>COMMIT</li>
<li>ROLLBACK</li>
<li>SAVEPOINT</li>
</ul>
<h3 id="case문">CASE문</h3>
<hr />
<ul>
<li>데이터의 값을 WHEN의 조건과 차례대로 비교한 후 일치하는 값을 찾아</li>
<li>THEN 뒤에 있는 결과값을 반환한다.<blockquote>
<p><strong>SELECT</strong>
  ENAME,
  DEPTNO,
  <strong>CASE</strong>
  <strong>WHEN</strong> DEPTNO='10' <strong>THEN</strong> 'NEW YORK'
  <strong>WHEN</strong> DEPTNO='20' <strong>THEN</strong> 'DALLAS'
  <strong>ELSE</strong> 'UNKNOWN'
  <strong>END</strong> <strong>AS</strong> <em>LOC_NAME</em>
  <strong>FROM</strong> EMP
  <strong>WHERE</strong> JOB='MANAGER'</p>
</blockquote>
</li>
</ul>
<h3 id="case문의-특징과-활용">CASE문의 특징과 활용</h3>
<hr />
<ul>
<li>표현식으로 사용</li>
<li>CASE 문은 하나의 값이나 결과를 반환하는 표현식이기 때문에</li>
<li>SELECT, ORDER BY, GROUP BY등의 구문 내에서 사용될 수 있다.</li>
<li>가독성 향상</li>
<li>복잡한 조건에 따른 값을 한눈에 파악할 수 있게 도와줘, 쿼리의</li>
<li>가독성과 유지보수성이 높아진다.</li>
<li>NULL 처리</li>
<li>조건에 해당하지 않는 경우 ELSE절에 없으면 NULL이 반환</li>
<li>중첩 사용 가능</li>
<li>CASE 문 안에 CASE문을 중첩해서 사용할 수 있다.</li>
<li>표준 SQL지원</li>
<li>대부분의 주요 데이터베이스 등에서 표준 SQL문법의 일부로 지원된다.</li>
</ul>
<p><br /><br /></p>
<h2 id="plprocedural-languagesql문">PL(Procedural Language)/SQL문</h2>
<hr />
<ul>
<li>원래 SQL문은 주로 데이터의 정의, 조작, 제어를 위한 언어</li>
<li>PL/SQL은 여기 조건, 반복문, 변수 선언, 예외처리와 같은</li>
<li>절차적 기능을 추가하여 복잡한 로직을 구현할 수 있게 해준다.</li>
</ul>
<h3 id="plsql-문의-구조">PL/SQL 문의 구조</h3>
<hr />
<ul>
<li>기본적으로 블록단위로 구성.하나의 블록은 세 부분으로 이루어져있다.</li>
<li>선언부(DECLARE) : 변수, 상수, 사용자 정의 타입을 선언</li>
<li>실행부(BEGIN ... END) : 실제 로직이 작성되는 부분</li>
<li>예외처리부(EXCEPTION) : 실행 도중 발생하는 오류를 처리하는 구문 작성</li>
</ul>
<pre><code class="language-java">DECLARE

    v_message varchar2(100); -- 변수느낌 let v_message;

BEGIN

    v_message := 'Hello, PL/SQL';

    DBMS_OUTPUT.PUT_LINE(v_message); -- console.log() 느낌

END;</code></pre>
<p><br /><br /></p>
<h3 id="if문">IF문</h3>
<hr />
<ol>
<li>IF 조건 THEN 실행문;
 END IF;</li>
<li>IF 조건 THEN 실행문;
ELSE 실행문;
END IF;<ol start="3">
<li>IF 조건 THEN 실행문;
ELSIF 조건 THEN 실행문;
ELSIF 조건 THEN 실행문;
ELSIF 조건 THEN 실행문;
END IF;
CHR(10) 이스케이프 문자 == \n<blockquote>
</blockquote>
</li>
</ol>
<strong>DECLARE</strong>
SALARY <strong>NUMBER</strong> := 5000; --LET SALARY = 5000;
<strong>BEGIN</strong>
<strong>IF</strong> SALARY &lt; 3000 <strong>THEN</strong> DBMS_OUTPUT.PUT_LINE('급여가 낮습니다');
<strong>ELSIF</strong> SALARY <strong>BETWEEN</strong> 3000 <strong>AND</strong> 7000 <strong>THEN</strong> DBMS_OUTPUT.PUT_LINE('급여가 중간입니다');
<strong>ELSE</strong> DBMS_OUTPUT.PUT_LINE('급여가 높습니다.');
<strong>END</strong> <strong>IF</strong>;
<strong>END</strong>;</li>
</ol>
<ul>
<li>SCORE 변수에 80을 대입하고</li>
<li>GRADE VARCHAR2(5)DP 어떤 학점인지 대입하여 출력하기</li>
<li>90점 이상은 A, 80점 이상은 B, 70점 이상은 C</li>
<li>60점 이상은 D, 그 이하는 F</li>
<li>당신의 점수 80점, 학점 B</li>
</ul>
<pre><code class="language-java">DECLARE

    SCORE NUMBER := 80;

    GRADE VARCHAR2(5);

BEGIN

    IF SCORE &gt;= 90 THEN GRADE := 'A';

        ELSIF SCORE &gt;= 80 THEN GRADE := 'B';

        ELSIF SCORE &gt;= 70 THEN GRADE := 'C';

        ELSIF SCORE &gt;= 60 THEN GRADE := 'D';

        ELSE GRADE := 'F';

    END IF;

    DBMS_OUTPUT.PUT_LINE('당신의 점수:'|| SCORE||', ' || '학점:' || GRADE );

END;</code></pre>
<p><br /><br /></p>
<h3 id="for문">FOR문</h3>
<hr />
<ul>
<li><p>FOR 변수 IN 시작값 .. END값 LOOP</p>
</li>
<li><p>반복하고자 하는 명령;</p>
</li>
<li><p>END LOOP;</p>
</li>
<li><p>옵션 REVERSE</p>
<blockquote>
</blockquote>
</li>
<li><p><em>BEGIN*</em></p>
</li>
<li><p><em>FOR*</em> I <strong>IN</strong> <strong>REVERSE</strong> 1..10 <strong>LOOP</strong>
DBMS_OUTPUT.PUT_LINE('I의 값 : ' || I);</p>
</li>
<li><p><em>END*</em> <strong>LOOP</strong>;</p>
</li>
<li><p><em>END*</em>;</p>
</li>
<li><p>1부터 10까지</p>
</li>
<li><p>X는 짝수입니다.</p>
</li>
<li><p>X는 홀수 입니다 출력하기</p>
<blockquote>
</blockquote>
</li>
<li><p><em>BEGIN*</em></p>
</li>
<li><p><em>FOR*</em> I <strong>IN</strong> 1..10 <strong>LOOP</strong></p>
</li>
<li><p><em>IF*</em> <strong>MOD</strong>(I,2) = 1 <strong>THEN</strong> DBMS_OUTPUT.PUT_LINE(I||'는 홀수입니다.');</p>
</li>
<li><p><em>ELSE*</em> DBMS_OUTPUT.PUT_LINE(I||'는 짝수입니다.');</p>
</li>
<li><p><em>END*</em> <strong>IF</strong>;</p>
</li>
<li><p><em>END*</em> <strong>LOOP</strong>;</p>
</li>
<li><p><em>END*</em>;</p>
</li>
<li><p>쿼리 결과를 행 단위로 반복처리할 때 사용</p>
<blockquote>
</blockquote>
</li>
<li><p><em>DECLARE*</em></p>
</li>
<li><p><em>CURSOR*</em> EMP_CURSOR <strong>IS</strong></p>
</li>
<li><p><em>SELECT*</em> EMPLOYEE_ID, FIRST_NAME <strong>FROM</strong> EMPLOYEES;</p>
</li>
<li><p><em>BEGIN*</em></p>
</li>
<li><p><em>FOR*</em> rec <strong>IN</strong> EMP_CURSOR <strong>LOOP</strong>
DBMS_OUTPUT.PUT_LINE('EMPLOYEE : '|| rec.EMPLOYEE_ID || ', NAME : ' || rec.FIRST_NAME);</p>
</li>
<li><p><em>END*</em> <strong>LOOP</strong>;</p>
</li>
<li><p><em>END*</em>;</p>
</li>
</ul>
<p><br /><br /></p>
<h3 id="while">WHILE</h3>
<hr />
<ul>
<li>WHILE 조건 LOOP</li>
<li>반복할 문장</li>
<li>END LOOP;</li>
<li>1 부터 10까지 총합 구해서 출력하시오</li>
<li>EX) 총합 : XX</li>
</ul>
<pre><code class="language-java">DECLARE

    I NUMBER := 0;

    X NUMBER := 0;

BEGIN

    WHILE I &lt;= 10 LOOP

     X := X + I;

         I := I + 1;

    END LOOP;

    DBMS_OUTPUT.PUT_LINE('총합은 : '|| X);

END;</code></pre>
<p><br /><br /></p>
<h2 id="plsql의-종류">PL/SQL의 종류</h2>
<hr />
<h3 id="1-익명블록">1. 익명블록</h3>
<hr />
<ul>
<li>이름 없이 한 번 실행되는 PL/SQL 블록이다</li>
<li>데이터베이스에 저장되지 않고 즉시 실행된다.</li>
<li>테스트, 일회성 작업, 간단한 스크립트 작성 등에 주로 사용된다.</li>
</ul>
<pre><code class="language-java">DECLARE

BEGIN

END</code></pre>
<h3 id="2-프로시저procdures">2. 프로시저(Procdures)</h3>
<hr />
<ul>
<li>데이터베이스에 저장되어 필요할 때마다 호출할 수 있는 이름이 있는</li>
<li>PL/SQL 블록이다.</li>
<li>하나의 요청으로 여러 SQL문을 실행시킬 수 있다</li>
<li>네트워크 소요시간을 줄여 성능을 개선할 수 있다.</li>
<li>기능 변경이 편하다.</li>
</ul>
<pre><code class="language-java">CREATE OR REPLACE PROCEDURE 프로시저명(

    매개변수 IN 데이터타입%TYPE

    매개변수 IN 데이터타입%TYPE

    매개변수 IN 데이터타입%TYPE

)IS

    함수 내에서 사용할 변수, 상수 선언

BEGIN

    실행할 문장

END;</code></pre>
<h3 id="3-트리거trigger">3. 트리거(trigger)</h3>
<hr />
<ul>
<li>특정 테이블 또는 뷰에 대한 DML 또는 DDL 작업이 발생할 때</li>
<li>자동으로 실행되는 PL/SQL코드이다.</li>
<li>JOBS 테이블에 INSERT를 해주는 프로시저 만들어보기</li>
</ul>
<p><br /><br /></p>
<h3 id="프로시저-선언-예시">프로시저 선언 예시</h3>
<hr />
<blockquote>
</blockquote>
<p><strong>CREATE</strong> <strong>OR</strong> <strong>REPLACE</strong> <strong>PROCEDURE</strong> MY_NEW_JOB_PROC(
P_JOB_ID <strong>IN</strong> JOBS.JOB_ID%<strong>TYPE</strong>,
P_JOB_TITLE <strong>IN</strong> JOBS.JOB_TITLE%<strong>TYPE</strong>,
P_MIN_SALARY <strong>IN</strong> JOBS.MIN_SALARY%<strong>TYPE</strong>,
P_MAX_SALARY <strong>IN</strong> JOBS.MAX_SALARY%<strong>TYPE</strong>
)
<strong>IS</strong>
<strong>BEGIN</strong>
<strong>INSERT</strong> <strong>INTO</strong> JOBS (JOB_ID, JOB_TITLE, MIN_SALARY, MAX_SALARY)
<strong>VALUES</strong>(P_JOB_ID,P_JOB_TITLE,P_MIN_SALARY,P_MAX_SALARY);
DBMS_OUTPUT.PUT_LINE('ALL DONE ABOUT '||' '||P_JOB_ID);
<strong>END</strong>;</p>
<p><br /><br /></p>
<h3 id="프로시저-호출-예시">프로시저 호출 예시</h3>
<hr />
<blockquote>
</blockquote>
<p><strong>CALL</strong> MY_NEW_JOB_PROC('IT','DEVELOPER',14000,20000);</p>
<p><br /><br /></p>
<h3 id="함수와-프로시저의-차이">함수와 프로시저의 차이</h3>
<hr />
<ul>
<li><p>함수는 반드시 하나 이상의 값을 반환해야한다. //오라클에서만</p>
</li>
<li><p>함수는 SQL문 내에서 사용할 수 있다.</p>
</li>
<li><p>함수는 주로 계산, 데이터의 가공, 값의 반환 작업에 사용</p>
</li>
<li><p>프로시저는 값을 반드시 반환할 필요는 없다.</p>
</li>
<li><p>프로시저는 SQL문 내에서 사용할 수 없다.</p>
</li>
<li><p>함수는 특정 작업이나 프로세스를 실행하기 위해 사용된다.</p>
</li>
</ul>