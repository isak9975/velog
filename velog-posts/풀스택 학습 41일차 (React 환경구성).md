<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/17338ecd-5219-4ba1-815d-5549eb95b5d7/image.jpg" /></p>
<h3 id="nodejs">Node.js</h3>
<hr />
<p>원래는 html에서 또는 개발자 창의 콘솔로 만 실행할 수 있던 javascript를 </p>
<p>컴퓨터에서 사용할 수 있도록 해주는 것.
<br /><br /></p>
<h3 id="자바스크립트를-브라우저-밖에서-사용하는-이유">자바스크립트를 브라우저 밖에서 사용하는 이유</h3>
<hr />
<p>자바스크립트를 클라이언트 언어뿐만 아니라 서버 언어로도 사용할 수 있다는 뜻.</p>
<p>이제 자바스크립스트로 도니 node 서버를 이용해 프론트엔드 서버를 개발한다.
<br /><br /></p>
<h3 id="npmnode-package-manager">NPM(Node Package Manager)</h3>
<hr />
<p>nodejs의 패키지 관리 시스템이다.</p>
<p>npm을 통해서 명령어를 통해서 라이브러리 설치가 가능해진다.</p>
<p><br /><br /></p>
<h1 id="개발환경-구성">개발환경 구성</h1>
<h3 id="1-nodejs--npm-설치">1. Node.js + Npm 설치</h3>
<hr />
<p>nodejs를 설치하면 npm이 자동으로 설치 된다.</p>
<p>인터넷으로 검색 후 lts 버전으로 다운로드</p>
<p>설치 후 cmd에서</p>
<pre><code class="language-java">node -v 

npm -v

npm version</code></pre>
<p>으로 각 프로그램의 버전 확인 가능.
<br /><br /></p>
<h3 id="2-작업폴더-만들기-및-작업폴더를-시작지점으로-터미널-켜기">2. 작업폴더 만들기 및 작업폴더를 시작지점으로 터미널 켜기.</h3>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/37c945aa-faf5-47e8-83c1-41d5feff7b38/image.png" />
<br /><br /></p>
<h3 id="3-터미널을-powershell-→-cmd로-교체-후">3. 터미널을 powershell → cmd로 교체 후</h3>
<p>“npx create-react-app 만들폴더명” 실행.</p>
<p>todo-react-app라는 폴더를 생성 및 react가 없을 경우 react설치.</p>
<p>만들어진 폴더 내부의 “package.json”에 메타데이터가 저장되어 있음.</p>
<pre><code>npx create-react-app todo-react-app</code></pre><p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/bd826858-77ef-4185-ba57-af9b9df480d1/image.png" />
<br /><br /></p>
<h3 id="4-만들어진-폴더로-이동-및-실행">4. 만들어진 폴더로 이동 및 실행</h3>
<pre><code class="language-java">-cd 만든폴더명
-npm start</code></pre>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/a6e4a783-221b-485d-add1-9f36fb630da2/image.png" />
그러면 React App이 실행된다.</p>
<p>React는 3000번 포트를 사용한다.</p>
<blockquote>
<p>localhost:3000</p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/b3a6f223-d1c0-4e21-a798-5eb856f70663/image.png" /></p>
<br />

<h4 id="구성-파일-설명">구성 파일 설명</h4>
<ul>
<li><em>package.json</em></li>
</ul>
<pre><code>프로젝트의 메타데이터.

사용할 node.js 의 패키지 목록.

사용할 버전도 명시되어있음.

필요한 패키지가 있다면 package.json 의 dependencies에 명시하고

npm install을 하면 node_modules에 설치된다.</code></pre><ul>
<li><p><em>package-lock.json</em></p>
<p>  어느 환경에서든 같은 버전의 패키지를 설치하기 위해 각</p>
<p>  패키지가 사용할 버전을 고정해 놓는다.</p>
<p>  보통 이 작업은 npm install 또는 create-reat-app 명령시 자동으로 실행된다.</p>
</li>
</ul>
<ul>
<li><em>manifest.json</em></li>
</ul>
<p>   웹 애플리케이션의 메타데이터를 정의하는 파일입니다.</p>
<ul>
<li><em>index.js</em></li>
</ul>
<pre><code>idnex.html과 함께 가장 처음으로 실행되는 자바스크립트 코드이다.

이 자바스크립트 코드가 리액트 컴포넌트를 root아래에 추가한다.

&gt; document.getElementById(’root’)
&gt; </code></pre><br />

<h3 id="material-ui-패키지-설치">material-ui 패키지 설치</h3>
<hr />
<pre><code class="language-java">npm install @mui/material @emotion/react @emotion/styled @mui/icons-material</code></pre>
<p>dependency에 추가하고 설치해야하는거 아니냐?</p>
<p>패키지의 이름을 정확하게 알고있다면 그럴 필요가 없다.
<br /></p>
<h3 id="material-ui">material-ui</h3>
<hr />
<p>UI를 위한 컴포넌트나 CSS를 작성하지 않아도 된다.</p>
<p><strong>@mui/material</strong></p>
<ul>
<li>Material-UI의 핵심 패키지로, 다양한 리액트 컴포넌트를 제공한다.</li>
<li>Material Design의 스타일과 원칙을 따르는 UI 컴포넌트를 구현하여, 개발자가 빠르고 쉽게 일관된 디자인의 사용자 인터페이스를 구축할 수 있도록 돕는다.</li>
</ul>
<p><strong>@mui/icons-material</strong></p>
<ul>
<li>Material Design 아이콘을 제공하는 패키지다.</li>
</ul>
<p><strong>@emotion/react</strong></p>
<ul>
<li>스타일을 정의하고 컴포넌트에 적용할 수 있는 기능을 제공한다.<br />
### 브라우저의 작동 원리

</li>
</ul>
<hr />
<p>브라우저가 주소창에 웹주소를 입력하면 → 브자우저는 http get 요청을 서버로 보냄.</p>
<p>html을 받은 브라우저는 두 단계를 거친 html을 브라우저에게 보여준다.</p>
<p><strong>1. 파씽</strong> : 렌더링을 위한 전처리 단계.  이때 브라우저 3가지일을 한다.</p>
<ol>
<li><p>html을 트리 자료구조의 형태인 DOM트리 형태로 변환</p>
</li>
<li><p>image,css,script등 다운로드 해야하는 리소스 다운.</p>
<p> (CSS는 다운 후 CSSSOM트리로 변환한다)</p>
</li>
<li><p>다운로드한 자바스크립트를 인터프리트,컴파일,파싱 실행한다.</p>
</li>
</ol>
<p><strong>2. 파싱을 마친 후 브라우저는 렌더링에 들어간다</strong></p>
<ol>
<li>DOM트리와 CSSOM 트리를 합쳐 렌더트리를 만든다.</li>
<li>트리의 각 노드가 브라우저의 어디에 배치될지, 레리아웃 정한다.</li>
<li>브라워저의 스크린에 렌터트리의 각 노드를 그려준다.</li>
</ol>
<p>JSX 문법으로 HTML, CSS엮어서 함수로 만든다</p>
<p>함수 → 어차피 자주 사용할 기능이라면 함수로 만들어서 재사용하자.
<br /><br /></p>
<h3 id="컴포넌트의-종류">컴포넌트의 종류</h3>
<hr />
<ol>
<li><p>함수형 컴포넌트</p>
<p> 정의 : 함수형 컴포넌트는 단순한 자바스크립스 함수로 props를 매개변수로 받아 jsx를 반환한다.</p>
<ul>
<li><p>구조분해 할당</p>
</li>
<li><p>let [A,B] = Arr; 하나씩 할당가능.</p>
</li>
<li><p><em>특징*</em></p>
<p>간단하고 , 리액트 훅을 사용하여 상태 및 라이프사이클 메서드를 관리할 수 있다.</p>
</li>
</ul>
</li>
</ol>
<p><br /><br /></p>
<h3 id="컴포넌트의-구성요소">컴포넌트의 구성요소</h3>
<hr />
<p> <strong>props(속성) (feat 매개변수)</strong></p>
<p>컴포넌트에 전달되는 데이터이다.</p>
<p>부모 컴포넌트에서 자식 컴포넌트로 데이터를 전달할 때 사용된다.</p>
<p>porps는 읽기 전용이며, 자식 컴포넌트에서 수정할 수 없다.
<br /></p>
<p> <strong>state(상태) (feat 변수)</strong></p>
<p>컴포넌트 내부에서 관리하는 데이터로, 컴포넌트의 동작이나 UI를 동적으로 변경할 수 있다.</p>
<p>상태는 컴포넌트 내에서 수정 가능하며, 상태가 변경되면 컴포넌트가 다시 렌더링된다.</p>
<p><br /><br /></p>
<h1 id="jsx">JSX</h1>
<hr />
<p><strong>React에서 사용하는 문법으로, javascript 코드 안에 html-like 구조를 작성할 수 있게 해준다.</strong></p>
<p>리액트 컴포넌트를 작성할 때 매우 유용하며, 가독성을 높이고 코드를 간결하게 작성할 수 있다.</p>
<p>jsx는 브라우저가 이해할수 없는 문법으로 Bable과 같은 도구를 통해 순수 JavaScript코드로 변환한다.
<br /></p>
<h3 id="문법">문법</h3>
<hr />
<p>JSX는 HTML과 매우 유사한 문법을 사용한다.</p>
<p>컴포넌트의 UI구조를 정의할 때 HTMl요소와 속성의 형태를 그대로 유지할 수 있다.</p>
<p><code>const element = &lt;h3&gt;Helo, world!&lt;/h3&gt;</code></p>
<p>JSX 내에서는 JavaScript 표편식을 { }를 사용하여 삽입할 수 있다.</p>
<pre><code class="language-java"> const name = ‘John’

 const element = &lt;h3&gt; Hello, {name}!&lt;/h3&gt;;</code></pre>
<h3 id="export">export</h3>
<hr />
<p><strong>컴포넌트를 다른 파일에서 사요할 수 있도록 내보내는데 사용된다.</strong></p>
<p>리액트 애플리케이션에서 모듈화는 중요한 개념으로, 각 파일이 독립적으로 작성되고, 필요한 곳에서 불러와 재사용될 수 있게 해준다.</p>
<p><strong>1. 기본 내보내기(Default Export)</strong></p>
<hr />
<pre><code class="language-jsx">

export default Greeting;

//이렇게 작성해도 된다.
export default function Greeting(props) {
return &lt;h1&gt;Hello, {props.name}!&lt;/h1&gt;;
}

// App.js
//기본 내보내기는 중괄호 없이 가져올 수 있다.
import Greeting from './Greeting';

function App() {
return &lt;Greeting name=&quot;John&quot; /&gt;;
}

export default App;</code></pre>
<p>↓</p>
<pre><code class="language-jsx">import React from 'react'

//함수형 컴포넌트의 정의
//컴포넌트의 이름을 정의할 때 대문자로 시작한다.
export function Greeting(props){
    //하나의 루트요소만 반환할 수 있다.
    //여러 요소를 반환할 때는 반드시 하나의 요소로 감싸야 한다.
    return &lt;h1&gt;Hello, {props.name}&lt;/h1&gt;
}</code></pre>
<p><br /><br />
<strong>2. 명명된 내보내기(Named Export)</strong></p>
<p>명명된 내보내기를 사용하면, 모듈에서 여러 값을 내보낼 수 있다.</p>
<p>각 값은 고유한 이름을 가지며, 이를 가져올 때도 이름을 정확히 일치시켜야 한다.</p>
<pre><code class="language-jsx">// App.js
//명명된 내보내기는 중괄호를 사용해야한다.
import { Greeting, Farewell } from './Greeting';</code></pre>
<p><br /><br /></p>
<h3 id="함수-호출하는-법">함수 호출하는 법</h3>
<hr />
<blockquote>
</blockquote>
<p>import 함수별명 from ‘./컴포넌트 주소’</p>
<blockquote>
</blockquote>
<p>&lt;함수명 /&gt;
 OR
&lt;함수명 props명 = “값” /&gt;</p>
<pre><code class="language-java">import Greeting from './Greetings.js';

&lt;Greeting name=&quot;John&quot; /&gt;</code></pre>
<p><br /><br /></p>
<h3 id="indexjs-설명">INDEX.js 설명</h3>
<hr />
<pre><code class="language-java">import React from 'react';//리액트를 사용하기 위해 import
import ReactDOM from 'react-dom/client';// 리액트 DOM을 사용하기 위해 import
import './index.css';// css import
import App from './App'; //App 컴포넌트 import
import reportWebVitals from './reportWebVitals';

//HTML 파일의 id=&quot;root&quot;인 요소를 찾고, 이 요소를 리액트 루트로 설정한다.

//ReactDOM.createRoot는 새로운 리액트 18의 루트 API를 사용하여 이 DOM 요소에 리액트 컴포넌트를 렌더링한다.
const root = ReactDOM.createRoot(document.getElementById('root'));

//root.render(&lt;React.StrictMode&gt;&lt;App /&gt;&lt;/React.StrictMode&gt;); : App 컴포넌트를 렌더링한다.
root.render(
  //React.StrictMode는 개발 모드에서만 활성화되는 도구로, 애플리케이션의 잠재적인 문제를 식별하고 경고를 제공하여 개발 중에 코드의 품질을 높이는 데 도움을 준다.
  &lt;React.StrictMode&gt;
    &lt;App /&gt;
  &lt;/React.StrictMode&gt;
);

reportWebVitals();</code></pre>
<p><br /><br /></p>
<h3 id="hook">Hook</h3>
<hr />
<p>함수형 컴포넌트에서 상태와 생명주기를 사용할 수 있게 해주는 기능</p>
<ul>
<li><p>useState()</p>
<p>  react에서 제공하는 메서드.</p>
<p>  상태를 관리하는 Hook의 일종.</p>
<p>  메서드를 호출하고 상태변수와 상태변수의 값을 바꿀 수 있는 setter 하나를 돌려준다.</p>
<blockquote>
<p>const[변수명,setter함수명] = useState(초기값)</p>
</blockquote>
<p>  <code>const[state,setState] = useState(”hi”)</code></p>
</li>
</ul>
<br />


<h4 id="변수state의-값이-변했을-때-새로고침을-안하고-어떻게-바뀌는가">변수(state)의 값이 변했을 때 새로고침을 안하고 어떻게 바뀌는가?</h4>
<hr />
<p>상태를 변경하는 setter 함수를 호출하면, 새로운 상태 값 또는 상태 업데이트 요청이 React의 상태 큐에 추가된다.</p>
<p>React는 큐(줄)을 처리하여 상태 변경 요청을 실제 상태에 반영한다.</p>
<p>이 과정에서 React는 비동기적으로 상태를 업데이트하므로, 여러 상태 변경이 있을 때 효율적으로 처리할 수 있다.</p>