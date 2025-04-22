<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/16997381-b7af-43e1-a09f-043f118ecb48/image.png" /></p>
<h3 id="-내용-">-내용-</h3>
<p>React에서 useState() 메서드 수업중 </p>
<p>오타없이 import 한것 같은데 오류가 나버렸다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/0ff8d49c-7d3d-416b-adae-66bc1fa1d36d/image.png" /></p>
<p><br /><br /></p>
<h3 id="-해결법-">-해결법-</h3>
<p>우선 오류의 내용처럼 제대로 import 된것같지 않아  Example.js를 확인 해 보았다.</p>
<p>Example.js 내부에서 함수를 export할때 문제 되는것 같아</p>
<p>export + exprt default를 해보았다. 그랬더니</p>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/84e8d903-2ea7-4cb0-9c63-c1b73a044267/image.png" /></p>
<p>오히려 오류가 엄청 많아져서 해석을 위해 AI의 도움을 받았는데</p>
<p>import가 잘안된것 같다고 확인해보라고 계속 그러더라.</p>
<p> import 한곳을 다시 봤는데 확장자명이 빠져있었다….</p>
<p>이걸 왜 이제 봤는지… 확장자 명 제대로 해주니 정상 동작하였다.</p>
<blockquote>
<p>import Example from './Example';</p>
</blockquote>
<p><br /><br /></p>
<h3 id="-알게된점-">-알게된점-</h3>
<p>VsCode에서는 파일만들때 확장자 잘 만들어야 겠다.</p>