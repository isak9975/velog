<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/e629907a-0832-4ad8-a2df-1aaeef639fac/image.jpg" /></p>
<h1 id="http-request-method">HTTP Request method</h1>
<hr />
<p><strong>서버 구조에서 요청(request)과 응답(response)가 이루어지는 방식을 의미한다.</strong></p>
<pre><code>ex) restful 하게 만든다.</code></pre><ul>
<li>쿼리스트링 : 사용자가 입력 데이터를 전달하는 방법 중 하나.
URL 뒤에 물음표 뒤 데이터를 덧붙여서 추가적인 정보 를 서버측에 전달.<blockquote>
<p>key=value&amp;key=value </p>
</blockquote>
</li>
</ul>
<br />

<h2 id="method-속성">method 속성</h2>
<hr />
<h4 id="get--조회-메서드">“GET” : 조회 메서드</h4>
<ul>
<li>특정 조건을 전달하고 싶으면 쿼리스트링으로 전달.<br /></li>
</ul>
<h4 id="post--전달한-데이터를-처리추가하는-메서드">“POST” : 전달한 데이터를 처리/추가하는 메서드</h4>
<ul>
<li>주로 신규 리소스 등록, 프로세스 처리에 사용<br /><h4 id="put--리소스를-대체수정하는-메서드">“PUT” : 리소스를 대체(수정)하는 메서드</h4>
</li>
<li>요청 메시지에 리소스가 있으면 덮어쓰고, 없으면 새로 생성한다.<br /><h4 id="patch--리소스의-일부분을-변경하는-메서드br">“PATCH” : 리소스의 일부분을 변경하는 메서드<br /></h4>
<h4 id="delete--리소스-제거하는-메서드br">“DELETE” : 리소스 제거하는 메서드<br /></h4>
</li>
</ul>
<br />

<h3 id="action-속성">action 속성</h3>
<hr />
<p>데이터를 처리하는 CGI 프로그램의 URL(목적지)</p>
<pre><code class="language-java">let myId = f.m_id.value;
    if(myId==''){
        alert('아이디는 필수사항입니다.')
        return 
    }

    let myAge = f.m_age.value;
    if(myAge==''){
        alert('나이는 필수사항입니다.')
        return 
    }

    let myPwd = f.m_pwd.value;
    if(myPwd==''){
        alert('비밀번호는 필수사항입니다.')
        return 
    }

    //전송받식
    f.method=&quot;GET&quot;;

    //목적지
    f.action=&quot;login.jsp&quot;;

    //입력된 데이터를 전송
    f.submit();</code></pre>
<ul>
<li>button type=submit이 있는데 이때 버튼을 누르면 바로 전송된다.<ul>
<li>지금 사용하지 않은 이유는 유효성 검사를 한번 진행하기 위해서</li>
</ul>
</li>
<li>마지막에 sumbit();을 진행해야만 데이터를 전송한다.<ul>
<li>반대로 하지 않으면 다른세팅을 해도 넘어가지 않는다.</li>
</ul>
</li>
<li>form 객체를 사용하면 편하게 컨트롤하여 넘길수 있다.<ul>
<li>key는 &quot;name&quot;값을 사용하므로 잘 작성해야한다.</li>
</ul>
</li>
</ul>