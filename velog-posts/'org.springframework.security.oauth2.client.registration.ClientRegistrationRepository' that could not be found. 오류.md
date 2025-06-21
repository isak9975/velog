<p>&lt;2025.06.18&gt;</p>
<h2 id="-내용-">-내용-</h2>
<p>OAuth2.0를 사용한 로그인 실습중 콘솔로 프로젝트를 실행하는 과정에서 제대로 동작하지 않는 문제가 생겼다.</p>
<pre><code class="language-java">./gradlew bootRun --args='--spring.profiles.active=dev --server.port=5000’</code></pre>
<p>위 명령령어를 사용했는데 아래와 같은 결과가 나왔다.</p>
<p>콘솔로 정확한 피드백을 받을 수 있어서 오류내용을 파해치기로 했다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/56c48d2a-b705-4d8e-9540-c73b36ff0b8b/image.png" /></p>
<br />

<h2 id="-해결법-">-해결법-</h2>
<p>오류의 내용을 해석해 보니 spring 부트에서 oauth에 대한 설정이 부족해서 생기는 문제였다.</p>
<p>혹시나 오타나 경로의 오류, 의존성 주입을 하지 않아 오류가 생긴것 같아서 작성한 코드를 다시 찾아봤지만. 오류나 나타날 만한 건덕지가 없었다.</p>
<p>gpt의 도움을 좀 받아서 오류 로그에서 어느부분이 어떤씩의 오류를 나타내는지를 검색해봤는데. 스프링부트가 처음에 실행될때 내가 설정한 application-dev.yml 파일이 제대로 읽히는지 확인할 수 잇는 방법을 알게 되었다.</p>
<pre><code class="language-java">2025-06-18T15:33:08.506+09:00  INFO 11732 --- [  restartedMain] com.korea.todo.TodoApplication           : No active profile set, falling back to 1 default profile: &quot;default”</code></pre>
<p>계속 우리가 정해준 application-dev.yml 파일이 제대로 읽히지 않고 있다는 것을 알았다.</p>
<p>실행 명령어로 경로를 지정해 준다는것이 안되면 다른 방법으로 경로를 주었다. </p>
<p>기본 파일인 application.yml 속에  기본설정의 파일을 쓰는 것이 아닌 application-dev.yml을 사용한다고 경로 설정을 진행했다.</p>
<pre><code class="language-java">spring:
  profiles:
    active: dev</code></pre>
<p>이렇게 되니 드디어 application-dev-yml 파일을 제대로 읽기 시작했다.</p>
<p>하지만 이번에는 정해준 포트인 5000이 아닌 8080으로 실행되려해서 fail이 떴다(Oracle로인해)</p>
<p>이로써 bootRun 이후에 적어준 옵션들이 제대로 동작하지 않는다는 것을 알게 되었다.</p>
<p>검색으로 build.gradle파일을 사용해서 실행명령어를 커스텀 할 수 있다는 것을 알게 되었고,</p>
<p>build.gradle 파일에 적어서 쓰는 명령어 대신, 직접적으로 포트와 경로를 설정해주었다.</p>
<pre><code class="language-java">bootRun {
    systemProperty 'spring.profiles.active', 'dev'
    systemProperty 'server.port', '5000'
}</code></pre>
<p>build.gradle 안의 내용은 잘 적용되었고 문제가 해결되었다.</p>
<br />

<h2 id="-알게된점-">-알게된점-</h2>
<ol>
<li>build.gradle을 사용하여 bootRun을 커스텀 할 수 있다는 것을 알게 되었다.</li>
<li>application.yml 파일을 그대로 쓰는것이 아닌 dev로 이름을 바꾸어 여러개 사용할 수 있다는 것을 알게 되었다.</li>
<li>원래 이클립스를 사용하여 쉽게 실행했었는데 콘솔로도 자바 프로젝트를 실행하는 것을 알게 되었다.</li>
</ol>