<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/134fbd00-0a82-487e-9da3-a59177746e10/image.png" />
&lt;2025.03.04&gt;</p>
<h2 id="html-콘솔-오류">HTML 콘솔 오류</h2>
<h3 id="-내용-">-내용-</h3>
<hr />
<p>수업중 강사님한테는 안뜨고 나한테만  </p>
<blockquote>
</blockquote>
<p>‘Refused to apply style from '<a href="http://127.0.0.1:5500/main.css'">http://127.0.0.1:5500/main.css'</a> because its MIME type ('text/html') is not a supported stylesheet MIME type, and strict MIME checking is enabled.’ </p>
<p>라는 내용의 오류가 계속 뜨는 현상을 발견.
큰 오류나 버그는 아니였지만 계속 보게 되니까 거슬려서 해결하기로 함.
<br /><br /><br /></p>
<h3 id="-해결법-">-해결법-</h3>
<hr />
<p>  문구를 해석해본 결과 css 파일의 문제인 것임을 알게됨.</p>
<p>  내 html 파일 내부에 사용하지도 않는데 들어가 있는 VSCODE 기본 제공 코드가 문제인것을 알게됨. </p>
<pre><code>&lt;link rel='stylesheet' type='text/css' media='screen' href='main.css'&gt; </code></pre><p>  삭제하여 해결.
<br /><br /><br /></p>
<h3 id="-알게된점-">-알게된점-</h3>
<hr />
<p>css 파일 경로가 이상하게 되면 홈페이지가 css파일 대신 html을 반환하게 되어 오류가 난다는것을 알게 되었고 다음에도 이 에러가 나온다면 경로 문제일것.</p>
<p>다음부터 기본코드를 만들때 CSS부분을 사용하지 않으면 삭제해야겠다.</p>