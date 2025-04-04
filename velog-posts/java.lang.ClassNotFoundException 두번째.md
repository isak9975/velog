<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/51a524d9-a8a7-4596-929b-6f65789245c1/image.png" /></p>
<p>&lt;2025.03.25&gt;</p>
<p>이클립스 JDK 오류2</p>
<h3 id="-내용-">-내용-</h3>
<hr />
<p>수업 한달이 지나 조의 편성이 달라지며 자리를 옮기게 되었다.</p>
<p>같은 수업이지만 그래도 개발환경이 달라져 세팅을 다시 하고 있는데</p>
<p>깃허브에서 클론해온 어제까지만 해도 잘 작동하던 코드가 갑자기 빨간줄이 잔뜩 뜨더니 오류가 나며 실행이 안되었다.</p>
<p>오류를 보니 직전에 만나봤던 녀석이였다.</p>
<blockquote>
<p><strong>java.lang.ClassNotFoundException</strong></p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/3e00222d-562c-4648-a2ab-14a725d879c2/image.png" /></p>
<p>또한 이번에는 새로운 오류도 보게 되었다.</p>
<blockquote>
<p>java compiler level does not match the version of the installed java project facet. eclipse</p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/6ad60214-7501-4b7f-b88c-aaa15946262d/image.png" /></p>
<p><br /><br /></p>
<h3 id="-해결법-">-해결법-</h3>
<hr />
<blockquote>
<p>java compiler level does not match the version of the installed java project facet. eclipse</p>
</blockquote>
<p>이 오류는 생각보다 간단했다.  해석해보면 컴파일러와의 버전이 맞지 않아 오류가 생겼다고 되어있다.</p>
<p>말 그래도 컴파일러와 프로젝트의 jdk 버전을 맞춰주면 되는데 compiler와 buildpath의 버전을 같게 해주면 해결이될 것이였다.</p>
<p>하지만 나 같은경우 한가지를 더 해줬어야 했는데</p>
<p>Project 우클릭 → properties → Project Facets에 있는 java의 버전까지 맞춰주어야 했다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/b49b472e-c816-4db1-9077-61476b80f3b8/image.png" /></p>
<p><strong>java.lang.ClassNotFoundException</strong></p>
<hr />
<p>우선 각종 곳에서 자바 JDK의 버전을 확인했다.</p>
<ol>
<li><p>Project 우클릭 → Propertise → JavaBuild path </p>
</li>
<li><p>Project 우클릭 → Propertise → Compiler</p>
<p> 우선 여기서 기존 수업에서 사용하던 17버전이 아닌 21버전으로 설정이 되어 있어 수정해 주었다.</p>
</li>
<li><p>Window → Preferences → Java → Installed JREs</p>
</li>
<li><p>Window → Preferences → Java → Compiler</p>
<p> 이 두가지에서도 21버전으로 되어있어서 추가로 맞는 버전으로 수정하니  문제가 해결되었다.</p>
</li>
</ol>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/5ca63779-eb26-48f5-9574-964bf43b0c0e/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/aae1d366-4688-4411-acd2-069e54866129/image.png" /></p>
<p><br /><br /></p>
<h3 id="-알게된점-">-알게된점-</h3>
<hr />
<ol>
<li>이클립스의 자세한 오류들은 problem에 나온다는것을 알게 되었다.</li>
<li>자바의 버전을 바꾸게 된면 많은곳에서 바꿔야 한다는것 을 알게되었다.</li>
<li>이제는 진짜 <strong>java.lang.ClassNotFoundException</strong> 오류 정복한것 같다.</li>
</ol>