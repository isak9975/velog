<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/115f5117-0262-44eb-8fc5-0b08bc13696a/image.jpg" /></p>
<h2 id="materialui의-컴포넌트">MaterialUI의 컴포넌트</h2>
<hr />
<h3 id="container">Container</h3>
<hr />
<p>레이아웃의 가로폭을 제한하고, 중앙 정렬 및 기본 패딩을 자동으로 적용해주는 컴포넌트</p>
<ul>
<li>주요 props
maxWidth : 최대 너비를 지정(xs, sm, md, lg, xl, false)</li>
</ul>
<h3 id="button">Button</h3>
<hr />
<p>다양한 스타일(variant) : text, contatined,outlined
 색상(color), 크기(size)를 지원하는 버튼 컴포넌트</p>
<h3 id="grid">Grid</h3>
<hr />
<p>CSS Grid 레이아웃 기반의 그리드 시스템
Flexbox 기반의 기존 Grid보다 행,열 제어가 직관적이고, rowSpacing, columnspacing으로
간격을 조절할 수 있다.</p>
<h4 id="주요-props">주요 props</h4>
<hr />
<ul>
<li>container : 그리드 컨테이너로 설정</li>
<li>item : 그리드 아이템으로 설정(생략해도 자동 감지)
xs(0), sm(600), md(900), lg(1200), xl(1536) : 각 브레이킹포인트별 차지할 컬럼수(기본 12분할)
브레이킹포인트 : 화면 너비 기준값</li>
<li>columns : 총 컬럼수 조정(기본 12)</li>
<li>rowSpacing, columnSpacing : 행,열 간격
<br /><br /><h3 id="textfield">TextField</h3>
</li>
</ul>
<hr />
<p>입력(input), 라벨(label), 헬퍼 텍스트(helperText), 에러표시(error)를 한번에
처리해줄 수 있는 컴포넌트</p>
<h4 id="주요-props-1">주요 props</h4>
<hr />
<ul>
<li>variant : 스타일 설정</li>
<li>label : 라벨 텍스트</li>
<li>helperText : 입력 하단 도움텍스트</li>
<li>error : 에러상태표시 true만 빨간색으로 강조</li>
<li>fullWidth : 가로 100%차지 여부</li>
<li>multiline : 여러줄 입력 여부</li>
<li>rows : multiline일 때 보여주는 줄 수</li>
<li>type : text, password, email 등 입력 타입</li>
</ul>
<p>react에서 style 줄 때는 js객체 형식으로 줘야한다.</p>
<p>App.js 에서 add'함수'를 전달받음.
props로 넘어온 내용을 받아서 사용할 준비가 끝남.</p>
<pre><code class="language-java">return(
//contianer
&lt;Grid container style={{marginTop:20}} &gt;
  &lt;Grid xs={11} md={11} item style={{paddingRight:8}}&gt;
    &lt;TextField color=&quot;secondary&quot;  placeholder=&quot;Add Todo here&quot; fullWidth
    value={item.title} onChange={onInPutChange}
    onKeyDown={enterKeyEventHandler}
    /&gt;
  &lt;/Grid&gt;
&lt;Grid&gt;
  &lt;Button onClick={onButtonClick} fullWidth style={{height:'100%'}} color=&quot;secondary&quot; variant=&quot;outlined&quot;&gt;+&lt;/Button&gt;
  &lt;/Grid&gt;
&lt;/Grid&gt;
)
}

export default AddTodo;</code></pre>
<h3 id="컴포넌트의-생명주기">컴포넌트의 생명주기</h3>
<hr />
<ol>
<li>마운트(컴포너트가 호출되서 화면에 보여질때)</li>
<li>업데이트(컴포넌트가 재렌더링 될 때)</li>
<li>언마운트(호출되서 종료되고 화면에서 사라질때)</li>
</ol>
<p><br /><br /></p>
<h3 id="useeffect">useEffect()</h3>
<hr />
<blockquote>
</blockquote>
<p>useEffect(함수, 의존성배열)<br />useEffect(( )⇒{ },[ ])</p>
<p>컴포넌트에서 부수효과(side effect)를 처리하기 위한 함수.</p>
<p>컴포넌트가 렌더링되면 첫번째 인자에 들어있는 함수가 실행된다.</p>
<h4 id="의존성-배열두번째인자">의존성 배열(두번째인자,[])</h4>
<hr />
<p>useEffect()의 실행 타이밍을 결정    </p>
<ol>
<li><p>없으면 렌더링이 될 때마다 실행(마운트+업데이트)</p>
<blockquote>
</blockquote>
<p>useEffect(함수)</p>
<ol start="2">
<li>빈배열 마운트시 한번만 실행<blockquote>
</blockquote>
useEffect(함수,[ ])</li>
<li>값명시 배열안의 값이 바뀔때마다 실행<blockquote>
</blockquote>
useEffect(함수,[count,state])</li>
</ol>
</li>
</ol>
<h4 id="클린업-함수언마운트-시점에-호출">클린업 함수(언마운트 시점에 호출)</h4>
<hr />
<ul>
<li><p>첫번째 인자에 들어있는 함수의 리턴함수
  (의존성배열에 들어있는 값이 변경되어 사이드 이펙트함수가 호출되기 직전)</p>
</li>
<li><p>생략가능 하다.</p>
</li>
</ul>
<pre><code class="language-java">useEffect(()⇒{

const id = setInterval(()⇒{

console.log(’1초마다 실행’)

//이부분이클린업 함수
return() ⇒ clearInterval(id);

},[])</code></pre>
<p><br /><br /></p>
<h3 id="useref">useRef()</h3>
<hr />
<p>변경 가능한 값을 찾아 DOM 요소에 직접 접근할때 사용.
<strong>값이 바뀌어도 재렌더링이 일어나지 않는다.</strong></p>
<pre><code class="language-java">const ref = useRef(initialValue) 형태로 호출되면

ref→{current:initialValue}

const inputRef = useRef(null)

&lt;input ref={inputRef}&gt; 

{current : &lt;input&gt;}

useEffect(()⇒{

inputRef/current.focus()

},[]);</code></pre>
<ul>
<li>이전값을 저장할 수 있다.</li>
</ul>
<ul>
<li>dom 조작할 때 많이 사용한다.</li>
</ul>