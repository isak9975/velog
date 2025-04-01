<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/1b2caf2d-d05b-4bb7-9613-6fe292960f78/image.png" /></p>
<h2 id="orcal-tomcat-port-충돌">Orcal, tomcat PORT 충돌</h2>
<h3 id="-내용-">-내용-</h3>
<hr />
<p>프로젝트 작업을 위해 톰켓 서버를 작동 시켰는데 실행되지 않았다. 오류 내용을 보니 내가 실행시키지 않은 tomcat 8080PORT가 사용중이라고 나와있다.
<br /><br /><br /></p>
<h3 id="-해결방법-">-해결방법-</h3>
<hr />
<p>cmd → netstat -a -o로 현재 열린 포트를 확인해보니 정말로 8080이 열려있었다.</p>
<p>taskill로 포트를 끄니 정상동작했다.</p>
<p>하지만 수업을 위해 ORACLE을 사용하니 ORACLE의 서버가 꺼져서 연동이 되지 않았다</p>
<p>아까 죽인 8080 PORT가 ORACLE 서버였던것이다. </p>
<p>ORCALE 서버를 다시키는 방법을 찾던중 오라클 PORT를 바꾸는 법을 알게 되었고 오라클의 PORT를 9090으로 옮겨 버렸다.</p>
<pre><code>exec dbms_xdb.sethttpport(9090);</code></pre><p><br /><br /><br /></p>
<h3 id="-알게된점-">-알게된점-</h3>
<hr />
<p>유명한 모든 프로그램이 다른 포트를 사용하지 않는다는 것을 알게 되었다.</p>
<p>ORACLE은 톰켓의 서버와 다르게 시작부터 켜져있고 프로그램을 다시 켠다고 켜지지 않았다.</p>
<p>포트가 겹친 첫 오류였던 것 같다.</p>