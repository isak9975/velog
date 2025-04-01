<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/2a02daae-7fed-4da4-a68a-7d7621afdf33/image.png" /></p>
<p>&lt;2025.03.21&gt;</p>
<h2 id="eclipse-라이브러리--jdk문제">Eclipse 라이브러리 + jdk문제</h2>
<h3 id="-내용-">-내용-</h3>
<p>이클립스의 플러그인을 여러가지 보던중, 코드 작성을 도와주는 CODEIUM이라는 플러그인을 보고 설치하였으나, 학습의 목적과 거리가 멀어 삭제하게 되었다.</p>
<p>별다른 생각이 없이 삭제를 했지만 갑자기 모든 코드에 빨간줄이 생기며 실행되지 않았다.</p>
<blockquote>
<p><strong>java.lang.ClassNotFoundException</strong></p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/ab824866-9d9b-4d9a-a5e9-e010ca13ad9b/image.png" /></p>
<p><br /><br /></p>
<h3 id="-해결법-">-해결법-</h3>
<p>검색을 해서 같은 문제를 겪는 분들의 힘들 빌리려고 했으나.</p>
<p>1) project 에서 clean  ⇒ 실패</p>
<p>2) Project → Properties → Java Build Path → Order and Export → JRE System Library (체크) ⇒ 실패</p>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/856cd5ae-8790-4f6d-ba47-68e646322031/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/d55d5811-6a77-4978-98fa-592a4bcbfd53/image.png" /></p>
<p>내가 사용한는 jdk 버전은 17인데 전부 이상하게 바뀌어있는것을 발견하였다.</p>
<p>뒤틀려 있는 jdk버전들을 하나하나 수정해주었다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/b05c8878-0305-4065-a257-f57fa27880fe/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/78b349c7-3007-41ce-8cce-ee1a57feeb42/image.png" /></p>
<p>해결하고 </p>
<p>Properties → Java Build Path</p>
<p>Properties → Java Compiler ⇒ jdk 버전 수정해주니 해결 되었다!</p>
<hr />
<p>갑자기 또 오류가 나서 찾아보니  - &gt; 프로젝트가 아닌 개별 파일에도 jdk 설정을 해줘야 한다고 해서 하니 해결 되었다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/d3dd89e4-af57-472b-9a34-a938ba6f6716/image.png" /></p>
<p><br /><br /></p>
<h3 id="-알게된점-">-알게된점-</h3>
<ol>
<li>프로젝트를 빌드 할때 필요한 파일들이 있으며, Modulepath, Classpath의 존재를 알게되었다.</li>
<li>프로젝트의 jdk와 컴파일러의 jdk가 다를수 있다는것을 배웠고 ,각각의 jdk설정법을 배웠다.</li>
<li>설정을 세부적으로 </li>
<li>플러그인 잘못 만지면 진짜 큰일나는것을 배웠다.</li>
</ol>