<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/deff438f-f54b-44a8-8ae0-30bd5c332866/image.jpg" /></p>
<h1 id="스프링-시큐리티">스프링 시큐리티</h1>
<p>Spring Security</p>
<hr />
<p>스프링 기반 어플리케이션에서 인증(Authentication)과 인가(Authorization)를 처리하기 위한 보안 프레임워크이다.</p>
<p>스프링 어플리케이션에서 보안과 관련된 다양한 요구 사항을 손쉽게 구현할 수 있도록 돕는다.</p>
<br />

<h2 id="주요개념">주요개념</h2>
<hr />
<p>*<em>1. 인증 *</em></p>
<ul>
<li><p>사용자가 누구인지 확인하는 과정</p>
</li>
<li><p>사용자 어플리케이션에 접근할 때 제공한 자격증명을 확인하여 신원을 검증하는 단계</p>
</li>
</ul>
<p><strong>2. 인가</strong></p>
<ul>
<li><p>인증된 사용자에게 어떤 리소스에 접근할 수 있는지 결정하는 과정</p>
</li>
<li><p>사용자에게 주어진 역할(Role)과 권한(Authority)에 따라 리소스에 대한 접근 권한을 부여한다.</p>
</li>
</ul>
<p><strong>3. 필터 기반 아키텍처</strong></p>
<ul>
<li><p>스프링 시큐리티는 필터 체인 기반으로 동작</p>
</li>
<li><p>HTTP 요청이 들어오면 여러 보안 필터들이 순차적으로 실행되어 요청을 처리하고, 보안 관련 로직을 적용한다.</p>
</li>
</ul>
<br />

<h3 id="스프링-시큐리티와-서블릿-필터">스프링 시큐리티와 서블릿 필터</h3>
<hr />
<ul>
<li><p>API가 실행될 때마다 기능이 실행되기 전 사용자 인증을 해야한다.</p>
</li>
<li><p>필터가 HTTP 요청과 응답을 가로채, 요청이 컨트롤러에 도달하기 전 또는 응답이 클라이언트에게 전달되기 전 필요한 전처리, 후처리를 수행하는데 사용된다.</p>
</li>
<li><p>주로 보안, 로그기록(로깅), 인코딩 설정, 데이터 압축 등의 잡업을 처리할 때 유용하다.</p>
</li>
<li><p>서블릿 필터를 구현하고 서블릿 필터를 서블릿 컨테이너가 실행하도록 설정만 해주면 된다.</p>
</li>
</ul>
<br />

<h3 id="jwtauthenticationfilterjava">JwtAuthenticationFilter.java</h3>
<hr />
<pre><code class="language-java">
//OncePerRequestFilter
//한 요청당 한 번만 실행되는 필터
//doFilterInternal() 메서드를 가지고 있다.

public class JwtAuthenticationFilter extends OncePerRequestFilter{ }
</code></pre>
<ul>
<li><p>HttpServletRequest : 요청 정보를 받아올 수 있는 인터페이스.</p>
</li>
<li><p>getMethod() : 요청메서드 확인 가능(GET,POST,PUT,DELETE)</p>
</li>
<li><p>getRequestURI() : 도메인 이후의 요청 경로를 반환</p>
</li>
<li><p>getProtocol() : 사용된 프로토콜과 버전을 반환</p>
</li>
</ul>
<br />

<h3 id="spring-boot-security-설정">Spring boot Security 설정</h3>
<hr />
<h4 id="csrf-cross-site-request-forgery">CSRF (Cross Site Request Forgery)</h4>
<p>기존의 사이트를 악상 사이트로 비슷한 URL 만들어서 인증하고 요청하는 해킹 방법.</p>
<p>사용자가 이미 로그인한 웹사이트(A)의 세션 쿠키를 가진 상태에서, 공격자가 만든 악성페이지를 열도록 유도하면, B페이지에서 A서버로 사용자 권한으로 위조된 요청을 보낼수도 있다.</p>
<p>disabled() : REST API 처럼 세션을 사용하지 않거나,  클라이언트가 토큰을 처리하기 어려운 경우 보호 기능을 끌 수 있다.</p>
<br />


<h3 id="스프링-부트-시큐리티를-이용한-토큰-인증-과정">스프링 부트 시큐리티를 이용한 토큰 인증 과정</h3>
<hr />
<p><strong>1. 사용자 로그인(토큰 발급)</strong>
    - 클라이언트가 사용자 이름과 비밀번호를 포함한 인증 요청을 서버로 보낸다.
    - 서버는 사용자 정보를 검증하고, 인증 성공 시 JWT 토큰을 발급한다.
    - 이 JWT 토큰은 인증된 사용자임 나타내며, Access Token으로 클라이언트에게 반환된다.</p>
<p><strong>2. 클라이언트 요청에 토큰 포함</strong>
    - 이후 클라이언트는 보호된 자원에 접근하기 위해 HTTP 요청의 Authorization 헤더에 발급받은 JWT 토큰을 포함한다.</p>
<p><strong>3. JWT 인증 필터에서 요청 가로채기</strong>
    - 스프링 시큐리티는 요청이 들어올 때 필터 체인을 통해 요청을 처리한다.
    - JwtAuthenticationFilter 같은 커스텀 필터를 사용하여 Authorization 헤더에서 JWT 토큰을 추출하고 검증한다.</p>
<p><strong>4. JWT 토큰 검증</strong>
    - 필터에서 추출한 토큰을 TokenProvider 같은 클래스를 사용하여 검증한다.</p>
<p><strong>5. 사용자 인증 정보 설정</strong>
    - 토큰이 유효하면 사용자 정보를 추출하고, 스프링 시큐리티의 SecurityContext에 인증 정보를 설정한다.</p>
<p><strong>6. 권한 확인</strong>
    - 설정된 인증 정보를 통해 사용자의 권한을 확인한다.</p>
<p><strong>7. 요청 처리 후 응답</strong>
    - 권한이 확인되면 요청을 처리하고, 결과를 클라이언트에 반환한다.</p>