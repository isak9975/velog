<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/0ca5ef91-a1e0-48a2-8570-55320e5868c8/image.jpg" /></p>
<h3 id="spring-data-jpa에서-기본적으로-제공하는-메서드">Spring Data JPA에서 기본적으로 제공하는 메서드</h3>
<hr />
<ol>
<li><p>저장</p>
<ul>
<li>save() : 엔티티를 저장하거나, 이미 조재하는 엔티티를 업데이트</li>
</ul>
</li>
<li><p>조회</p>
<ul>
<li><p>findById(Object id) : Id로 엔티티를 조회한다. 반환값은 Optaionl이다.</p>
</li>
<li><p><strong>findAll()</strong> : 모든 엔티티를 조회한다.</p>
</li>
</ul>
</li>
<li><p>삭제</p>
<ul>
<li><strong>delete()</strong> : 특정 엔티티를 삭제한다.</li>
</ul>
</li>
<li><p>카운트</p>
<ul>
<li><strong>count()</strong> : 엔티티의 총 개수를 반환한다.</li>
</ul>
</li>
<li><p>존재여부 확인</p>
<ul>
<li><strong>existsById()</strong> : 특정 ID가 존재하는지 확인한다.</li>
</ul>
</li>
</ol>
<h3 id="직접작성하는-메서드">직접작성하는 메서드</h3>
<hr />
<p>쿼리메서드 : 메서드 이름을 기반으로 자동으로 쿼리를 생성하는 기능을 제공한다.</p>
<h4 id="접두어">접두어</h4>
<hr />
<ol>
<li>findBy : 주어진 조건으로 엔티티를 찾는다.</li>
</ol>
<pre><code class="language-java">    findByName(String name): //이름으로 사용자 조회</code></pre>
<ol start="2">
<li>countBy : 특정 조건을 만족하는 레코드 개수를 반환</li>
</ol>
<pre><code class="language-java">    countByAge(int age); //</code></pre>
<ol start="3">
<li>existsBy : 특정 조건을 만족하는 레코드가 존재하는지 확인</li>
</ol>
<pre><code class="language-java">    exsistsByEmail(String email)</code></pre>
<ol start="4">
<li>deleteBy : 주어진 조건에 해당되는 레코드 삭제</li>
</ol>
<pre><code class="language-java">    deleteByName(String name);</code></pre>
<p>5 . 조건의 결합</p>
<ul>
<li><strong>And / Or</strong></li>
</ul>
<pre><code class="language-java">      //&lt;And&gt;
      findByNameAndEmail(String name, String email)
      //&lt;Or&gt;
      findByNAmeOrEmail(String name, String email)</code></pre>
<ul>
<li><p>*<em>isNull/IsNotNull *</em></p>
<p>null 또는 null이 아닌 조건을 처리</p>
</li>
</ul>
<pre><code class="language-java">      findByEmailsNull()

      findByEmailsNotNull()</code></pre>
<p><br /><br /></p>
<h2 id="jpqljava-persistence-query-language">JPQL(Java Persistence Query Language)</h2>
<hr />
<p>@Query 어노테이션을 사용하여 직접 쿼리를 작성할 수 있다.</p>
<p>JPQL 이라고 하고 엔티티 객체를 대상으로 쿼리를 작성한다.</p>
<h3 id="jpql의-특징">JPQL의 특징</h3>
<hr />
<ul>
<li>데이터베이스 테이블 대신 JPA 엔티티 객체를 대상으로 쿼리를 실행한다.</li>
<li>테이블 이름이나 컬럼 대신 엔티티 클래스의 이름과 필드를 사용하여 쿼리를 작성한다.</li>
<li>이 때문에 JPQL쿼리는 데이터베이스 독립적이며, 데이터베이스의 스키마에 의존하지 않는다.</li>
<li>JPQL은 SQL과 매우 유사한 문법을 사용하지만, 엔티티 객체를 다룬다는 점에서 차이가</li>
<li>예를 들어, SQL에서 select * from user 는 select u from Users u 로 표현한다.</li>
</ul>
<p><br /><br /></p>
<h2 id="로그log">로그(Log)</h2>
<hr />
<ul>
<li><p>소프트웨어 시스템이나 어플리케이션 동작상태, 이벤트가 발생했을 때 그 내용들을 기록한 정보.</p>
</li>
<li><p>개발자, 운영자 또는 시스템이 해당 어플리케이션의 상태를 파악하거나 문제 해결을 위해 사용한다.</p>
</li>
<li><p>주로 어플리케이션의 실행 흐름, 오류 또는 성능 문제를 추적하고 분석하는데 매우 중요한 도구다.</p>
</li>
</ul>
<br />

<h3 id="로그의-주요-목적">로그의 주요 목적</h3>
<hr />
<ol>
<li><p><strong>디버깅</strong></p>
<p> 어플리케이션에서 발생한 문제나 버그를 추적하고 원인을 파악하기 위해 사용된다.</p>
</li>
<li><p><strong>모니터링</strong></p>
<p> 어플리케이션이 예상대로 작동하는지 확인하고, 시스템 성능을 모니터링 하기 위해 사용된다.</p>
</li>
<li><p><strong>문제해결</strong></p>
<p> 어플리케이션이 예상치 못한 상황이 발생했을 때, 로그를 통해 그 문제를 해결하는 데 필요한 정보를 얻을 수 있다.</p>
</li>
<li><p><strong>보안감사</strong></p>
<ul>
<li><p>어플리케이션에 대한 보안 감사 및 추적을 위해 사용된다.</p>
</li>
<li><p>시스템에 대한 접근 시도나 비정상적인 활동을 로그로 기록하여, 보안 위협을 감지하고 대응할 수 있다.</p>
</li>
</ul>
</li>
</ol>
<br />


<h3 id="로그의-주요-구성요소">로그의 주요 구성요소</h3>
<hr />
<ol>
<li><p>타임스탬프 : 로그가 기록된 시간</p>
</li>
<li><p>로그레벨(Log level) : 로그의 중요도를 나타낸다.</p>
<ul>
<li><p>TRACE : 가장 낮은 수준의 로그</p>
</li>
<li><p>DEBUG : 개발 과정에서 주로 사용되는 디버깅 정보</p>
</li>
<li><p>INFO : 시스템의 정상적인 동작을 나타내는 정보</p>
</li>
<li><p>WARNING : 예상치 못한 상황이 발생했지만, 시스템이 정상적으로 동작하는 경우</p>
</li>
<li><p>ERROR : 오류가 발생했으며, 시스템이 정상적으로 동작하지 않는 경우</p>
</li>
<li><p>FATAL : 매우 심각한 오류로, 시스템이 더 이상 동작할 수 없는 경우.</p>
</li>
</ul>
</li>
<li><p>메시지 : 로그에 기록된 이벤트에 대한 설명</p>
</li>
<li><p>이벤트 소스 : 로그가 기록된 위치</p>
</li>
</ol>
<br />

<h2 id="slf4j">Slf4j</h2>
<h4 id="simple-logging-facade-for-java">Simple Logging Facade for Java</h4>
<hr />
<ul>
<li>Java 어플리케이션에서 사용하는 로깅 프레임워크에 대한 통합된 인터페이스를 제공하는 로그 추상화 라이브러리이다.</li>
<li>Slf4j는 로그를 작성하는 표준 인터페이스를 제공하고, 실제로 로그를 기록하는 것은 Logback, Log4j 같은 다른 로깅 프레임워크가 담당하는 방식이다.</li>
</ul>
<h3 id="역할">역할</h3>
<hr />
<ol>
<li>로깅 프레임워크의 추상화</li>
<li>호환성 유지</li>
</ol>