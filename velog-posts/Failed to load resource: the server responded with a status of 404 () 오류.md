<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/d51853e2-bf1e-4953-a09a-ba72b702c0a0/image.png" />
<img alt="업로드중.." src="blob:https://velog.io/c6a2d521-f8d7-4f1d-8adb-1a13225a9b59" />
&lt;2025.03.11&gt;</p>
<h2 id="html-경로-오류">HTML 경로 오류</h2>
<h3 id="-내용-">-내용-</h3>
<hr />
<p>github의 무료 웹 호스팅 실습을 하던 중에 index.html 말고는 전부 깨지는 현상이 발견됨.</p>
<p><code>Failed to load resource: the server responded with a status of 404 ()</code></p>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/174aacfe-d532-460b-b5d3-1ac7f160c250/image.png" /></p>
<p><br /><br /><br /></p>
<h3 id="-해결법-">-해결법-</h3>
<hr />
<p>경로 문제라는 것을 알고 검색을 해봤지만 나와 맞는 정보가 나오지 않았음.</p>
<p>그래서 강사님이 배포하신 홈페이지를 들어가 내 코드의 경로와 하나씩 비교하다가 경로 따라 들어가는건 비슷한데  경로 앞의 “/” 하나 다른걸 발견하게 됨.</p>
<p>수정하니까 해결됨.</p>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/586e53a4-ebcd-4c74-936b-b6901d46eb4c/image.png" /></p>
<pre><code>                                                &lt;내코드&gt;</code></pre><p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/b71cf4f5-6374-45bc-bc44-8ba0aa046084/image.png" /></p>
<pre><code>                                            &lt;강사님 코드&gt;</code></pre><p><br /><br /><br /></p>
<h3 id="-알게된점-">-알게된점-</h3>
<hr />
<p>주소 앞의  ‘/’ 하나로 경로가 바뀌게 된걸 보고 경로가 어식으로 타고 들어가는지 알게 되었으며, 글자 하나로도 모든게 깨질수 있다는 경로의 중요함을 알게되었다.</p>