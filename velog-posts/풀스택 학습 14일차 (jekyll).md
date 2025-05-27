<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/b0db1fbb-db51-480c-b273-14b3faed43c7/image.png" /></p>
<h2 id="배포deploy">배포(deploy)</h2>
<hr />
<p>html, css, js → 우리 컴퓨터에서만 볼 수 있음(로컬 환경).</p>
<p>배포란 웹 페이지를 인터넷이랑 연결하여 누구나 접속해 볼 수 있는 상태로 만드는 행위.</p>
<p>웹페이지 배포 절차</p>
<ol>
<li>웹 페이지를 컴퓨터에 저장한다.</li>
<li>컴퓨터를 인터넷에 연결한다.</li>
<li>컴퓨터의 설정을 변경하여 외부에서 접속할 수 있도록 한다.</li>
<li>외부인이 접속을 요청을 할 때마다, 컴퓨터가 웹페이지를 보여줌.</li>
</ol>
<p>이때 사용된 컴퓨터를 서버(server)라고 부른다.</p>
<h3 id="웹-호스팅-서비스">웹 호스팅 서비스</h3>
<hr />
<p>서버 용도로 사용되는 컴퓨터는 일반 컴퓨터보다 비싸다.</p>
<p>인터넷 회선도 무료가 아님.</p>
<p>서버를 많이 구매한 다음, 인터넷 회선에 가입하고, 서버를 비려주는 회사들이 존재한다.</p>
<p>이러한 서비스를 웹 호스팅이라고 부른다.</p>
<p>서버컴퓨터는 사양이 아주 높기 때문에 하나의 서버에서 홈페이지를 수십, 수백개까지 운영할 수 있다.</p>
<p>cafe24, 가비아 등 </p>
<p>AWS,</p>
<p>github페이지 </p>
<p>깃허브에서는 무료로 웹 페이지를 호스팅 할  수 있는 서비스를 제공한다.</p>
<p>레포지토리로 이동 → settings → 왼쪽 메뉴에 pages → branch에 master or main 설정</p>
<p>주의해야 할 점 </p>
<p>root폴더에 index.html이 존재해야 한다.</p>
<h3 id="지킬">지킬</h3>
<hr />
<p>프레임 워크</p>
<p>지킬생태계(eco-system)</p>
<p>생태계라고 부를만큼 다양한 사용자들이 존재한다.</p>
<p>지킬로 만든 자기 작품을 많이 공유한다.</p>
<p>MIT라이센스</p>
<p>이 소프트웨어를 누구든지 무상으로 제한 없이 사용해도 좋다.</p>
<p>단, 완성된 소프트웨어의 중요한 부분의 저작권 표시를 해야한다.</p>
<p>소프트웨어의 원작자는 아무런 책임을 지지 않는다.</p>
<h3 id="리포지토리의-fork">리포지토리의 Fork</h3>
<hr />
<p>리포지토리의 복제본을 만드는 방식중 하나이다.</p>
<p>원본 레포지토리의 내용이 수정되거나, 삭제되더라도 현재의 버전을 간직해두고 사용할 수 있다.</p>
<p>현재 버전의 레포지토리를 박제하는 행위</p>
<h3 id="템플릿의-이해">템플릿의 이해</h3>
<hr />
<p>우리가 가져온 템플릿의 HTML, CSS, JS를 건드릴 필요없이</p>
<p>내용 정도만 수정을 하면 된다.</p>
<h3 id="git-명령어">git 명령어</h3>
<hr />
<p>git init → 해당 폴더를 git이 관리하겠다</p>
<p>git remote add 레포url → 원격 repo와 연결하겠다</p>
<p>git add . → 해당 폴더에 있는 파일ㅇ르  Stage에 올리겠다</p>
<p>git commit -m init →  git이 관리하도록 commit을 하겠다</p>
<p>git push origin master → commit된 정보를 원격 repo에 올리겠다.</p>
<h3 id="jekyll-명령어">jekyll 명령어</h3>
<hr />
<p>jekyll serve -&lt; jekyll 프로젝트를 실행</p>
<p>버전 에러 날때</p>
<p>bundle install</p>
<p>bundle update</p>
<p>bundle add webric</p>
<p>—</p>
<p>gem uninstall jekyll → 지킬 삭제</p>
<p>gem install jekyll -v ‘4.3.3.’ → 특정 버전을 다운로드 받을 수 있다.</p>
<h3 id="jekyll-파일-설명">jekyll 파일 설명</h3>
<hr />
<p>_config.yml → 지킬 환경설정</p>
<p>_data 폴더 → 웹사이트에서 활용할 데이터를 지정할 수 있다.</p>
<p>-includes 폴더 → 웹 페이지에 포함시킬 html 파일 저장.</p>
<p>_layouts 폴더 → 웹 페이지의 뼈대를 결정</p>
<p>_posts 폴더 → 블로그 게시물을 저장</p>
<p>_sass 폴더 → CSS의 기능을 확장시켜 더 효율적이고 유지보수하기 쉬운 스타일 시트를 작성할 수 있도록 도와준다.</p>
<p>__site 폴더 → 빌드가 끝난 코드가 저장된다.</p>
<p>코드를 다 작성하고 마지막에 빌드라는 작업을 통해 데이터가 조립되어 배포에 적합한 상태로 다듬어 진다.</p>
<p>실제로 배포할 때는 빌드된 코드만 사용한다. </p>
<p>bundle exec jekyll serve</p>