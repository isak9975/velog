<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/abd0e1a0-de8b-4df9-bd4e-fec63f24e7aa/image.jpg" /></p>
<h3 id="objectassign">Object.assign()</h3>
<ul>
<li>자바 스크립트에서 객체의 속성을 다른 객체에 복사할 때 사용하는 함수이다.</li>
<li>주로 여러 개의 객체를 하나의 객체로 합칠 때 사용한다.</li>
<li><strong>target</strong> : 속성을 복사할 대상 객체</li>
<li><strong>source</strong> : 속성을 복사할 하나 이상의 원본 객체들<blockquote>
</blockquote>
Object.assign(target,...source);</li>
</ul>
<p>ex)</p>
<pre><code class="language-java">const item = Object.assign({},tasks);</code></pre>
<p><br /><br /></p>
<h1 id="asyncstorage">AsyncStorage</h1>
<hr />
<p>앱 내에 데이터를 로컬에 영구적으로 저장할 수 있도록 해주는 비동기 저장소 시스템.</p>
<p>리액트 할 때 로그인 하면 토큰을 반환을 받고, localStorage에 저장을 했는데 그거랑 비슷함.</p>
<ul>
<li>AsyncStorage는 비동기로 작동을 하고 JSON 기반으로 key-value형태로  데이터를 저정한다.</li>
</ul>
<p><strong>- 비동기로 작동하기 때문에 async + await를 꼭 사용해야한다.</strong></p>
<ul>
<li>사용자가 로그인한 상태를 유지하고 싶을 때, 최근 검색어, 설정값, 토글 상태 등을 기억하고 싶을 때 주로 사용한다.<blockquote>
<p>npm install @react-native-async-storage/async-storage --legacy-peer-deps</p>
</blockquote>
</li>
</ul>
<br />

<h4 id="사용법">사용법</h4>
<hr />
<p>value에 넣을 때 JSON.stringfy로 변환을 해서 저장해야 한다.</p>
<blockquote>
</blockquote>
<p>AsyncStorage.setItem(key,value)</p>
<pre><code class="language-java">const item = async () =&gt; {
  await AsyncStorage.setItem(’user’,JSON.stringfy(user));
}</code></pre>
<p>실제 저장 되는 내용은 </p>
<ul>
<li><p>key : user</p>
</li>
<li><p>value : “{\”id\”:123,\”name\”:\”kang\”}”</p>
</li>
</ul>
<br />

<h4 id="저장된-데이터를-확인하는법">저장된 데이터를 확인하는법</h4>
<hr />
<ul>
<li>.getItem을 사용하면 key에 해당하는 value 값을 가져올 수 있다.<blockquote>
</blockquote>
const data = await AsyncStorage.getItem(key)</li>
</ul>
<br />

<h4 id="저장된-전체-key-불러오기">저장된 전체 key 불러오기</h4>
<hr />
<ul>
<li>.getAllKeys()를 사용하게 되면 전체 key를 가져올 수 있다.<blockquote>
</blockquote>
const keys = await AsyncStorage.getAllKeys();</li>
</ul>