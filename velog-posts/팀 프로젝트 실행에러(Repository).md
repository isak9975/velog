<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/eeb65e16-b848-44f8-a58d-d143f281008e/image.png" /></p>
<p>&lt;2025.03.12&gt; </p>
<h2 id="팀-프로젝트-실행에러repository">팀 프로젝트 실행에러(Repository)</h2>
<h3 id="-내용-">-내용-</h3>
<hr />
<p>  팀원들과의 git merge 후 충돌이 발생하지 않았었으나 프로젝트가 실행이 되지않음.</p>
<p>  팀원이 작성한 MessageRepository 와 MessageEntity에서 문제가 발생한 것 같음.</p>
<h3 id="-해결방법-">-해결방법-</h3>
<hr />
<ol>
<li><p>MessageEntity의 메서드에서 순환참조가 발생한것을 확인
<code>public void  deleteByReceiver() {this.deleteByReceiver}</code></p>
<p>순환참조 되는 부분을 수정함.
this.deleteByReceiver = true;</p>
</li>
<li><p>MessageRepository에 선언된 함수에서 순차적으로 오류가 발생하는 것을 확인.</p>
<p> 코드를 확인 해보니 Repository의 메소드에 들어가는 변수명들이 Entity와 다르게 카멜표기법으로 작성되어있는것을 확임함.</p>
<p> 메서드의 이름에 있는 변수들의 카멜 표기법을 제거하니 문제가 해결되었다. </p>
<p> +다른곳에 선언된 메서드명도 수정</p>
</li>
<li><p>MessageRepository에서 선언된 메서드의의 이름과 다른것을 발견 (delete~ → deleted~)
메서드명 수정으로 해결하였다.
<br /><br /></p>
</li>
</ol>
<h3 id="-알게된점-">-알게된점-</h3>
<hr />
<p>  Repository를 사용하여 메서드를 선언할때 변수의 이름을 앞글자만 대문자를 써야한다는 것을 다시한번 알게되었다.</p>
<p>  Repository를 사용할대는 사용법에 주의해야한다는것을 알게되었다.</p>