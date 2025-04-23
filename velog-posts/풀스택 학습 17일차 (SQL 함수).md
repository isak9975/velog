<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/88c0c9e9-6e4f-4908-a064-47ecb71c5c7b/image.jpg" /></p>
<h3 id="정렬order-by">정렬(Order by)</h3>
<hr />
<p>-질의 결과에 반환되는 행들을 특정 기준으로 정렬하고자 할때 사용</p>
<p>-SELETE 정의 가장 마지막에 기술</p>
<p>-ASC : 오름차순 (기본값)(생략가능)</p>
<p>-DESC : 내림차순 (생략불가능)
<br /><br /></p>
<h3 id="함수적-종속성">함수적 종속성</h3>
<hr />
<p>-하나의 테이블에서 한 컬럼의 값(X)가 다른 컬럼의 값(Y)를 결정하는 관계</p>
<ul>
<li><p>완전 함수 종속</p>
<p>  PK를 가지고 나머지 값을 알 수 있다.</p>
<p>  EX) 주민번호 하나를 가지고 이름, 나이, 주소를 알 수 있다.</p>
</li>
</ul>
<ul>
<li><p>부분함수 종속</p>
<p>  여러개의 컬럼으로 PK가 이루어져있을 때 PK중 하나의 속성만으로도 종속성이 성립될때</p>
<p>  EX) 사원번호와 부서번호로 이루어진 PK가 있을때</p>
<p>  사원번호 만으로도 이름, 주소, 전화번호를 알 수 있다</p>
</li>
<li><p>이행함수종속</p>
<p>  X →Y, Y→ Z 할때 X→Z 를 결정해버리는 종속성</p>
<p>  EX) 사원번호를 통해 이름을 알 수 있고, 이름을 통해 주소를 알수 있을 때, 사원번호를 통해 주소를 알 수 있다.</p>
</li>
</ul>
<p><br /><br /></p>
<h3 id="이상현상anoramally">이상현상(Anoramally)</h3>
<hr />
<ul>
<li>삽입이상</li>
</ul>
<ul>
<li>갱신이상</li>
</ul>
<ul>
<li>삭제이상</li>
</ul>
<p><br /><br /></p>
<h3 id="정규화">정규화</h3>
<hr />
<p>너무 정규화를 진행하면 조회가 느려지기에</p>
<p>대부분 3차까지만 진행한다.</p>
<ul>
<li><p>1차 정규화(1NF)</p>
<p>  도메인은 원자값이어야 한다.</p>
<p>  도메인이 원자값 → 하나의 컬럼에는 하나의 데이터만</p>
</li>
<li><p>2차 정규화(2NF)  : 부분 함수 종속 제거</p>
<p>  1NF를 만족하고 부분함수 종속을 제거해야한다.</p>
<p>  1차 정규화의 조건을 먼저 만족해야함. + </p>
</li>
<li><p>3차 정규화(3NF) : 이행 함수 종속 제거</p>
<p>  1,2 NF를 만족하고 이행함수 종속을 제거해야한다.</p>
</li>
</ul>
<p><br /><br /></p>
<h3 id="sql함수">SQL함수</h3>
<hr />
<ul>
<li><p>ASCII(’값’)</p>
</li>
<li><p>CHR(’숫자’)</p>
</li>
<li><p>RPAD(데이터, 고정길이, 문자)</p>
</li>
<li><p>LPAD(데이터,고정길이,문자)</p>
</li>
<li><p>TRIM(문자열)</p>
</li>
<li><p>RTRIM()</p>
</li>
<li><p>LTRIM()</p>
</li>
<li><p>INSTR(’문자열’,’문자’,시작위치,몇번째) :  문자 위치 반환</p>
</li>
<li><p>INITCAP(데이터) : 첫문자를 대문자로 변환</p>
</li>
<li><p>LENGTH() : 문자열 길이 반환</p>
</li>
<li><p>CONCAT() : 두문자열을 연결(오라클에서만)</p>
</li>
<li><p>SUBSTR(데이터, 시작위치, 길이) : 문자열의 시작 위치부터 길이만큼 자른 후 반환</p>
</li>
<li><p>LOWER()</p>
</li>
<li><p>UPPER()
<br /><br /></p>
<h3 id="sql-숫자-함수">SQL 숫자 함수</h3>
</li>
</ul>
<hr />
<ul>
<li><p>ABS(숫자)</p>
</li>
<li><p>ROUND(숫자,자리수) : 반올림</p>
</li>
<li><p>FLOOR(숫자) : 올림</p>
</li>
<li><p>TRUNC(숫자) : 버림</p>
</li>
<li><p>SIGN() : 부호판단 0 ⇒ 0, NULL ⇒ NULL</p>
</li>
<li><p>CEIL() : 올림</p>
</li>
<li><p>MOD() : 나머지</p>
</li>
<li><p>POWER() : 제곱
<br /><br /></p>
<h3 id="sql-날짜-함수">SQL 날짜 함수</h3>
</li>
</ul>
<hr />
<ul>
<li><p>ADD_MONTHS(날짜,개월)</p>
</li>
<li><p>MONTHS_BETWEEN(최근,옛날)</p>
</li>
<li><p>NEXT_DAY(기준날자,’원하는 요일’)</p>
</li>
<li><p>NVL(컬럼, 치환할 값)</p>
</li>
<li><p>NVL2(컬럼, NULL아닐때, NULL일때)</p>
</li>
<li><p>RANK() OVER(ORDER BY )</p>
</li>
<li><p>DENSE_RANK( )</p>
</li>
<li><p>COUNT( )</p>
</li>
<li><p>MIN( )</p>
</li>
<li><p>MAX( )</p>
</li>
<li><p>SUM( )</p>
</li>
<li><p>AVG( )
<br /><br /></p>
<h3 id="order-by절">ORDER BY절</h3>
</li>
</ul>
<hr />
<blockquote>
</blockquote>
<p>ORDER BY 컬럼 ASC/DESC</p>
<h3 id="group-by-절">GROUP BY 절</h3>
<hr />
<ul>
<li>그룹화(GROUP BY)
특정 테이블에서 소그룹을 만들어 결과를 분산시켜 결과를 얻고자 할때</li>
</ul>
<h3 id="having-절">HAVING 절</h3>
<hr />
<ul>
<li>GROUP BY로 집계된 값 중 조건을 추가하는 것</li>
<li>WHERE 절과 HAVING절의 차이</li>
<li>HAVING절은 GROUP BY와 함께 사용해야 하며</li>
<li>집계함수를 사용하여 조건절을 작성하거나</li>
<li>GROUP BY 컬럼만 조건절에 사용할 수 있다.</li>
</ul>