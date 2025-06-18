<p>&lt;2025.06.16&gt;</p>
<h1 id="aws-elastic-beanstalk-502-bad-gateway-오류"><strong>AWS-Elastic Beanstalk 502 Bad Gateway 오류</strong></h1>
<h2 id="-내용-">-내용-</h2>
<p>AWS에 관한 실습을 하던중 배포 과정의 시작인 ElasticBeanstalk에서 502 Bad Gateway가 떠버렸다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/e2875b8b-2a2e-4194-8752-bc297df60602/image.png" /></p>
<p>단순 오타로 인한 오류인줄 알고 오류를 열심히 찾아봤지만 오타로 인한 오류는 아닌것 같았다.</p>
<br />

<h2 id="-해결법-">-해결법-</h2>
<p>혼자 여러 검색을 해보려 했으나 정보가 너무 부족했다. java나 react와 다르게 오류에 대한 이유 또는 위치를 전혀 알수 없었다.</p>
<p>강사님의 도움으로 ElasticBeanstalk → 선택 → 로그 에서 로그를 확인할 수 있다는것을 확인했고 이를 확인 할 수 있게 된다.</p>
<p>로그를 확인 해본 결과 RDS에 접속할수 없어서 503이 나온다는걸 알게 되었다.</p>
<p>RDS에 설정된 아이디-패스워드와 백엔드의 application.yml에 작성한 아이디-패스워드가 문제가 있다고 판단하고 이부분에서 수정과 업로드를 반복하였으나 해결하지 못했다.</p>
<p>→ RDS 접속에 문제</p>
<p>로컬환경에서 mysql로 엔드포인트+아이디+비밀번호를 이용하면 접속할 수 있다는것을 검색으로 알게 되었고 접속을 하니 잘 접속이 되었다! </p>
<p>→ 아이디와 패스워드가 문제가 아님, RDS의 문제가 아님.</p>
<p>아이디+ 패스워드 + 엔드포인트는 몇번씩 확인해서 접속이 안되는것이니 권한, 즉 인바운드에 문제가 있다고 생각을 하고 여러가지 인바운드 규칙을 넣어 봤으나 변화가 없었다.</p>
<h3 id="최후의-방법으로-elasticbeanstlak을-다시-생성하기로-했는데-잘-작동을-하였다">최후의 방법으로 ElasticBeanstlak을 다시 생성하기로 했는데 잘 작동을 하였다!!</h3>
<p>마지막에 만든 ElasticBeanstlak과 기존에 있던 것을 비교해본 결과.</p>
<p>RDS의 버전이 서로 달라 접속하지 못했던것으로 결론이 났다.
<img alt="" src="https://velog.velcdn.com/images/isak9975/post/e5fdcb0d-4453-490c-a6c4-1b128ec0ac4c/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/b970691e-4b27-4b80-bc5b-6595a081975f/image.png" /></p>
<br />

<h3 id="-알게된점-">-알게된점-</h3>
<ol>
<li>버전 맞추는것이 중요 하다는것을 참 많이 들었었지만 매번 체감은 되지 않았었다. 하지만 이번 경험으로 너무 제대로 느꼈다. (거의다 오타때문에 오류 난거라)</li>
<li>ElasticBeanstlak → RDS로 따로 만들지 않고 한번에 만들었지만 버전 문제가 있는것을 보고, 지금까지는 버전이 원인이 아닐거라고 생각했지만 버전 또한 오류의 원인이 될 수 있다는걸 배웠다.</li>
<li>오류를 고치는 과정에서 ElasticBeanstalk과 RDS 에 대한 실습을 너무 제대로 해서 나중에 내 프로젝트를 AWS에 배포하기에 한결 수월할 것 같다.</li>
</ol>