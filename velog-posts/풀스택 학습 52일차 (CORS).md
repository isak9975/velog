<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/6774c0a9-e0be-4995-9d74-c48e1745217d/image.jpg" /></p>
<h3 id="corscross-origin-resource-sharing">CORS(Cross-Origin Resource Sharing)</h3>
<hr />
<ul>
<li><p>프론트+백엔드 개발자들은 필히 알아야 하는 용어.</p>
</li>
<li><p>교차 출처 리소스 공유</p>
</li>
</ul>
<h3 id="출처origin">출처(origin)</h3>
<hr />
<ul>
<li>프로토콜과 호소트주소 그리고 포트번호를 합친것.</li>
</ul>
<blockquote>
<p>ex) <a href="http://localhost:3000">http://localhost:3000</a></p>
</blockquote>
<ul>
<li>서버의 위치를 찾아가기 위해 필요한 가장 기본적인 것들을 합쳐놓은것.</li>
</ul>
<h3 id="동일-출처-정책same-origin-policy">동일 출처 정책(Same-Origin Policy)</h3>
<hr />
<ul>
<li><p>브라우저는 기본적으로 보안을 위해 동일 출처 정책이라는 규칙을 따른다.</p>
</li>
<li><p>같은 출처에서 로드된 웹사이트만 서로 데이터를 주고 받을 수 있다는 내용이다.</p>
</li>
<li><p>즉, 웹 페이지가 한 출처에서 로드되었을 때, 다른 출처에서 데이터를 요청하는 것을 제한하는 정책.</p>
</li>
<li><p>이 정책은 보안을 위해, 악의적인 웹사이트가 사용자의 브라우저를 이용해 다른 출처에서 데이터를 가져오지 못하게 막는 역할을 한다.</p>
</li>
</ul>
<h3 id="webmvcconfigjava">WebMvcConfig.java</h3>
<hr />
<ul>
<li><p>@Configuration</p>
<p>  스프링에서 해당 클래스를 설정 클래스로 인식하고 bean 으로 등록.</p>
</li>
<li><p>WebMvcConfigurer</p>
<ul>
<li><p>스프링 MVC의 기본설정을 내가 조절하고 싶을 때 사용한다.</p>
</li>
<li><p>스프링 MVC는 여러가지 기본설정(뷰 리졸버, 메시지 컨버터, CORS등)을 가지고 있다.</p>
</li>
</ul>
</li>
</ul>
<ul>
<li>.allowedOrigins(&quot;/<a href="http://localhost:3000/">http://localhost:3000</a>&quot;) // 리액트 서버 경로
React 어플리케이션이 실행되는 도메인에서 오는 요청을 허용하겠다.</li>
<li>.allowedMethods(&quot;GET&quot;,&quot;PUT&quot;,&quot;POST&quot;,&quot;DELETE&quot;)
HTTP 메서드를 허용하겠다.</li>
<li>.allowedHeaders(&quot;*&quot;)
모든 헤더를 허용하겠다.</li>
<li>.allowCredentials(true)
쿠키나 인증 정보를 포함한 요청을 허용하겠다</li>
<li>.maxAge(MAX_AGE_SECS);
브라우저가 서버로부터 받은 응답을 일정 시간 동안 저장하고, 그 시간 내에 동일한 요청이 있을 경우 서버에 다시 요청하지 않고 저장된 응답을 재사용한다.</li>
</ul>
<pre><code class="language-java">public class WebMvcConfig implements WebMvcConfigurer{
    private final long MAX_AGE_SECS = 3600; //1시간 
    //브라우저가 CORS 요청 결과를 캐싱하는 최대 시간 설정
        //캐싱이란 : 자주 쓰는 정보를 미리 저장해 뒀다가, 다음에 같은 정보가 필요할 때.
        //저장소에서 꺼내쓰는 기법.
    //한시간동안 저장해뒀다가 그 안에 또 요청하면 저장된거 보여주겠다.


    //registry : 스프링이 내부에서 생성해서 넘겨주는 CROS 설정용 객체이다.
    @Override
    public void addCorsMappings(CorsRegistry registry) {

        registry.addMapping(&quot;/**&quot;)
        .allowedOrigins(&quot;/http://localhost:3000&quot;
            .allowedMethods(&quot;GET&quot;,&quot;PUT&quot;,&quot;POST&quot;,&quot;DELETE&quot;) 
                .allowedHeaders(&quot;*&quot;)
                    .allowCredentials(true)
                        .maxAge(MAX_AGE_SECS);

    }

}</code></pre>
<h3 id="리액트의-렌더링">리액트의 렌더링</h3>
<hr />
<ul>
<li><p>리액트는 브라우저에 보이는 HTML DOM 트리의 다른버전인 ReactDOM을 가지고있다.</p>
</li>
<li><p>어떤 이유에서 컴포넌트의 상태가 변하면 ReactDOM은 이를 감지하고 컴포넌트 함수를 다시 호출함으로써 변경된 부분의 HTML을 바꿔준다.</p>
</li>
<li><p>HTML 이 업데이트되면 우리는 변경된 결과를 눈으로 확인할 수 있다.</p>
</li>
</ul>
<h3 id="무한루프에-빠진-리액트">무한루프에 빠진 리액트</h3>
<hr />
<ul>
<li><p>렌더링이 가장 처음 일어나는 순간, 리액트는 ReactDOM트리가 존재하지 않는 상태에서 처음으로 각 컴포넌트 함수를 호출해 자신의 DOM 트리를 구성한다.</p>
</li>
<li><p>어플리케이션에서 갖아 처음 호출되는 함수는 App()</p>
</li>
<li><p>내부에서 axios를 이용해서 Todo API를 호출한다.</p>
</li>
<li><p>axios를 사용한 API 호출은 비동기 호출이기 때문에 API 호출 후 응답이 올 때까지 기다리지 않는다.</p>
</li>
<li><p>기다리지 않고 함수를 반환했기 때문에 Add Todo Here과 같은 입력 필드나  +버튼을 볼 수 있다.</p>
</li>
</ul>
<h3 id="이때-사용하는것이-useeffect이다">이때 사용하는것이 useEffect()이다.</h3>
<h3 id="api-configjs">api-config.js</h3>
<hr />
<p>API를 호출하는 주소를 하드코딩 할 수 있지만 실제 도메인을 사용하는 것을 염두에 두면 좋은 방법은 아니다.</p>
<p>설정파일에서 어플리케이션이 사용할 백엔드 url을 동적으로 가져오도록 구현해, 이후 도메인이 바뀌는 경우를 대비하자.</p>
<p>api-config.js → 벡엔드 도메인을 설정</p>
<p>ApiService → 백엔드 호출을 함수화</p>
<p>앞으로 백엔드에 대한 호출이 필요하면 call함수만 호출하면 된다.</p>
<ul>
<li><p>조회</p>
<p>  call(”/todo”,”GET”)</p>
</li>
<li><p>추가</p>
<p>  call(”/todo”,”POST”,item)</p>
</li>
<li><p>삭제</p>
<p>  call(”/todo”,”DELETE”,item)</p>
</li>
<li><p>수정</p>
<p>  타이틀 변경을 위해 input의 필드에서 사용자가 입력을 받아올때 editEventHandler() 에서 item을 바로 넘겨버리면 한글자씪 입력할 때마다 HTTP 요청을 보내게 된다.</p>
<ul>
<li><p>이는 비효율적이기 때문에 수정을 완료한 시점에서 HTTP 요청을 보내고 싶다.</p>
</li>
<li><p>입력이 끝나서 수정이 불가능한 상태로 바뀌는 시점.</p>
</li>
</ul>
</li>
</ul>