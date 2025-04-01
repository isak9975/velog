<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/fb84715d-be5c-49a4-a248-9512889b5ef8/image.png" /></p>
<p>&lt;2025.03.19&gt;</p>
<h2 id="pssql-프로시저-작성-오류">PS/SQL 프로시저 작성 오류</h2>
<h3 id="-내용-">-내용-</h3>
<p>PS/SQL, 프로시저 수업중, 작성한 프로시저가 제대로 등록되지 않음 + 등록된 프로시저가 제대로 동작하지 않음.</p>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/f57f28af-3a6d-4a1e-9b2a-6cae4d740e37/image.png" />
<br /><br /><br /></p>
<h3 id="-해결방법-">-해결방법-</h3>
<ol>
<li><p>제대로 등록되지 않음 오류.</p>
<p> 프로시저를 잘 작성하더라고 부분만 인식하는 경우가 있어서</p>
<p> 작성한 프로시저문을 전부 드래그 후 등록하면 제대로 등록이 된다.</p>
</li>
<li><p>프로시저가 제대로 동작하지 않음 오류.</p>
<p>다른 오류를 해결할때 IS 뒤에 DELCLARE를 사용했었는데</p>
<p>이 부분 때문에 프로시저가 제대로 등록 &amp; 작동하지 않아서 제거하였다.</p>
<p> <strong><em>해결방법은 간단했으나 알게된점이 많아서 작성하였다.</em></strong>
<br /><br /><br /></p>
</li>
</ol>
<h3 id="-알게된점-">-알게된점-</h3>
<ol>
<li>잘 작성했는데 안될경우 CREAT ~ END 한번에 드래그 후 Ctrl + Enter</li>
<li>IS는 DECLARE와는 다르게 구문을 정의할때도 쓰여서 생략이 불가능하다</li>
<li>IS의 역할 =&gt; 프로시저 구문 정의 + 변수선언(DECLARE)</li>
<li>프로시저에는 IN을 사용할 수 있지만 PL/SQL문에서는 불가능하다</li>
<li>프로시저에서는 DECLARE를 사용하면 오류가 난다.</li>
<li>프로시저는 제대로 동작하지 않아도 등록이 가능하다(무섭)</li>
</ol>