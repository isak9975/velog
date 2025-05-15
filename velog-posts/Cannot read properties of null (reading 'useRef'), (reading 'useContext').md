<h2 id="리액트-라이브러리-설치-오류">리액트 라이브러리 설치 오류</h2>
<h3 id="-내용-">-내용-</h3>
<p>리액트 실습 중에 Router 사용중 오류가 발생하였다.</p>
<p>배운대로 빠짐없이 한것 같은데 정상동작을 하지 않았다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/bc7bc960-9000-4143-9226-b7d40c806676/image.png" />
<img alt="" src="https://velog.velcdn.com/images/isak9975/post/04ed3b74-7efa-40f1-9abf-a6cc5ad70d5f/image.png" /></p>
<h3 id="-해결법-">-해결법-</h3>
<p><strong>첫째</strong>로 오류의 내용을 해석할때 useRef, useContext가 제대로 인식되지 않는 문제인 것같았다.</p>
<p>router를 사용하는데 왜 훅이 필요한지 몰랐지만, react 의 기본 훅이니까 필요한가 보다 하고 import를 해주었다.</p>
<blockquote>
<p>import {useContext, useRef} from ‘react’</p>
</blockquote>
<p><strong>둘째</strong>로 블로그에 검색을 해보니, 라이브러리를 제대로 설치하지 않아서 생기는 문제라고 하였다.</p>
<p>처음에 사용하기 전에 명령어를 사용해서 설치한것이 확실히 기억나서 이건 아니겠지 생각했다.</p>
<p>그래도 혹시 몰라서 확인해 보니 package.json을 확인해보니 설치가 되어있지 않았다…</p>
<p>알고보니 내가 다른 프로젝트들을 한번에 모아놓고 사용을 하고 있었는데, 설치 할때 경로 설정을 잘못하여 다른 패키지에 설치한것이였다.</p>
<p>라이브러리를 다시 설치하니 정상 동작하였다.</p>
<blockquote>
<p>react - router - dom</p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/077eeae4-7bd8-43ea-9116-c3ca91707dce/image.png" /></p>
<h3 id="-알게된점-">-알게된점-</h3>
<p>라이브러리 설치할때 경로 제대로 보고 설치해야겠다….</p>