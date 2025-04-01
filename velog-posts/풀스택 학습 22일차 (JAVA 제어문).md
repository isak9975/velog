<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/9cacc2ee-99e7-43a4-a0f1-fb55015a95e7/image.jpg" /></p>
<h2 id="제어문control-statement">제어문(control statement)</h2>
<hr />
<p>일반적으로 프로그램에 포함된 실행문은 순차적으로 실행이된다.
위에서 아래로, 좌에서 우로
하지만 순차적으로나 실행한다면 프로그램이 매우 길어지거나
표현하기 어려운 상황이 발생할 수 있다
<br /><br /><br /></p>
<h2 id="조건문">조건문</h2>
<hr />
<p>조건식에 따라서 프로그램의 흐름을 제어할 수 있는 분법이다.
조건식 : true, false 로 결과가 반환되는 식
조건문의 종류
if : 고려해야하는 조건이 적으면
switch : 고려해야하는 조건이 많으면
-특정 개수에 따라 반드시 써야하는건 아니다</p>
<h3 id="단순if문">단순if문</h3>
<hr />
<p>조건문 중에서도 가장 기본이 되는 명령문이다</p>
<blockquote>
</blockquote>
<p>if(조건식){
    조건식이 참일 때 실행할 문장
}</p>
<p>만약 실행해야 하는 명령이 하나라면 중괄호를 생략할 수 있다.</p>
<blockquote>
<p>if(조건식) 조건식이 참일때 실행할 문장</p>
</blockquote>
<p>if 문만 사용하면 조건이 참일때만 흐름을 제어할 수 있다.
조건이 거짓일 때도 흐름을 제어하고 싶다면 if-else 문을 사용한다.</p>
<blockquote>
</blockquote>
<p>if(조건식){
    조건이 참일때 실행할 명령
} else {
    조건이 거짓일때 실행할 명령
}</p>
<p><br /><br /><br /></p>
<h4 id="중괄호에-대하여">중괄호에 대하여</h4>
<hr />
<p>중괄호를 생략 할수도 있지만, 사용하면 가독성이 좋을 뿐 아니라 
코드의 해석이 용이하고 버그를 찾아 수정하는데 도움이 되므로 중괄호를 쓰는 습관을 기르자</p>
<p>중괄호를 사용할 때는 들여쓰기를 하는 것이 좋다.
들여쓰기에는 탭(tab)이나 공백(스페이스바)를 이용하는데
혼용하여 사용하지 않고 <strong>한가지 방법으로 일관되게</strong> 사용하는것이 좋다
<br /><br /><br /></p>
<h3 id="if-else-문">if-else 문</h3>
<hr />
<p>비교해야할 조건이 여러개 있는 경우 사용하는 문법
if문안에 두개 이상의 조건식과 논리연산자를 사용할수도 있지만
더욱 코드를 간결하게 하고 가독성을 높이기 위한 방법으로
if.else if문을 구현한다.</p>
<blockquote>
</blockquote>
<p>if(조건식1){
조건식1이 참일 때 실행할 명령
else if(조건식2){
    조건식1이 거짓이고 2가 참일때
else if(조건식3){
    조건식1,2,가 거짓이고 3이 참일때
else {
    위의 조건이 모두 거짓일 때 실행할 문장.
}</p>
<p>else-if 문의 개수에는 제한이 없다.</p>
<p>하지만 너무 많은 else-if문을 사용한다면
프로그램의 실행 속도가 현저히 느려질 수 있기 때문에
다른 방법을 함께 고려해야한다.</p>
<p>else문은 필요없다면 생략이 가능하다</p>
<pre><code class="language-java">int favorite = 7;
if(favorite &gt; 5) {
    System.out.println(&quot;좋아하는 숫자가 5보다 큽니다.&quot;);
}else if(favorite == 7) {
    System.out.println(&quot;좋아하는 숫자는 7입니다&quot;);
}</code></pre>
<p>효율적인 프름으로 제어하기 위해 if문과 else if문의 조건문의
위치를 잘 고려해야한다.</p>
<h4 id="if문의-중첩">if문의 중첩</h4>
<p>제어문은 자유롭게 중첩해서 사용할 수 있다.</p>
<blockquote>
</blockquote>
<p>if(조건식1){
if(조건식2){
        조건식1과 2가 모두 참이어야 실행할 명령
    }
}
<br /><br /><br /></p>
<h3 id="switch문">switch문</h3>
<hr />
<p>switch 문의 비교값으로 사용 가능한 자료형</p>
<p>1) 정수(byte, short,int )
2) 문자형(char)
3) 문자열(String)</p>
<blockquote>
</blockquote>
<p>switch(비교값){
    case 조건식:
        //        비교값과 조건값이 일치할 때 실행할 문장.
        break;
    default : 
        비교값과 일치하는 조건값이 없을 때 실행할 문장
}</p>
<pre><code class="language-java">int num = 7;

switch(num) {
    case 1:
        System.out.println(&quot;num 은 1입니다&quot;);break;
    case 7:
        System.out.println(&quot;num 은 7입니다&quot;);break;
    default : 
        System.out.println(&quot;num은 1도 7도 아닙니다.&quot;);
        break;
}//end switch</code></pre>
<p>비교값과 조건값의 타입이 일치해햐한다.
case 에 들어가는 조건값들은 겹칠 수 없다.</p>
<p>char 형 변수 ch가 알파벳(대문자 또는 소문자)일때 true인 조건식
<br /><br /><br /></p>
<h4 id="심화">심화</h4>
<hr />
<p>java 12이상으로 업데이트 되면서
switch 의 문법이 새롭게 만들어졌다.
조건절에 복수개의 값을 사용하는것이 가능해졌다.
 표현식을 이용하는게 가능하다.</p>
<p>JAVA12 부터 사용가능한 화살표 CASE문
기존의 SWITCH문과는 달리 CASE에 해당하는 절만 실행되고
그 후의 CAS는 실행되지 않는다</p>
<pre><code class="language-java">switch(day) {
    case 
        &quot;Monday&quot;,&quot;Tuesday&quot;,&quot;Wendsday&quot;,&quot;Thursday&quot;, &quot;Friday&quot; -&gt;System.out.println(&quot;평일&quot;);
    case
        &quot;Saturday&quot;, &quot;Sunday&quot;-&gt; System.out.println(&quot;주말&quot;);
    default
        -&gt; System.out.println(&quot;잘못된 입력입니다&quot;);
}</code></pre>
<p><br /><br /><br /></p>
<h4 id="ascii코드-활용법">ASCII코드 활용법</h4>
<hr />
<pre><code class="language-java">ch&gt;='A' &amp;&amp; &lt;= 'Z' || ch&gt;='a'&amp;&amp;ch &lt;='z'
char ch = 't';
if(ch &gt;= 97 &amp;&amp; ch &lt;= 122 || ch&gt;=65&amp;&amp;ch &lt;=90) {
    System.out.println(&quot;true&quot;);    
}</code></pre>
<p><br /><br /><br /></p>
<h2 id="for문">for문</h2>
<hr />
<p>주로 반복 횟수가 정해져있을 때 싸용하는 문법</p>
<blockquote>
</blockquote>
<p>for(초기식; 조건식; 증감식){
    반복하고자 하는 명령
}</p>
<p>초기식 : 반복을 하기 위한 시작값으로 변수를 하나 초기화 한다.
조건식 : 반복을 위한 종료값으로 비교연산자를 많이 사용한다
증감식 : 초기식에 있는 변수의 증감시켜주는 역할을 한다.</p>
<pre><code class="language-java">for(int i=0; i&lt;=3; i++) {
System.out.println(i);
}</code></pre>
<p>초기값 밖에다 쓸수 있음, 대신 자리는 마련해야함
int i=0;
for(;i&lt;=3;) {
증감값도 밖에다 쓸 수 있음, 대신 자리는 마련해야함
System.out.println(i);
i++;
}</p>
<blockquote>
</blockquote>
<p>for문안에 또 다른 for문을 사용하는 경우
반복문을 반복하는 것
for(초기식;조건식;증감식){
    for(초기식;조건식;증감식){
        반복하고자 하는 명령
    }
}</p>
<pre><code class="language-java">for(int i = 0;i&lt;3;i++) {
for(int j=0;j&lt;3;j++) {
System.out.println(i+&quot; &quot;+j);
}//end 2
}//end 1</code></pre>
<pre><code class="language-java">        //A B C D
        //E F G H 
        //I J K L 
int n1 = 0;
for(int i = 1; i&lt;=3;i++) {
for(int j = 1; j&lt;=4;j++) {
char ch='A';
System.out.printf(&quot;%c&quot;,ch+n1);
n1 = j ;
}
System.out.println();
n1 += 1;
}</code></pre>
<h3 id="while문">while문</h3>
<hr />
<p>while 문은 반복 횟수가 정해져있을 때 할 수 도 있지만
반복 횟수를 정확히 모를때 유용하다.</p>
<p>초기식;</p>
<blockquote>
</blockquote>
<p>while(조건식){
    반복하고자 하는 명령
    증감식;
}</p>
<pre><code class="language-java">int i =1;

while(i&lt;4) {

System.out.println(i);
i++;
}</code></pre>
<p><br /><br /><br /></p>
<h3 id="do-while문">do-while문</h3>
<hr />
<p>while 문과 같이 조건을 만족할 때까지 반복한다.
다만, while 문과 다른 점은 먼저 루프를 한 번 실행한 후 
조건식을 검사한다는 점이다.</p>
<pre><code class="language-java">Scanner scanner = new Scanner(System.in);

int kor=0;
int math =0;
int en =0;
boolean state = true;

do {
System.out.println(&quot;국어 점수를 입력해주세요&quot;);
kor = scanner.nextInt();
System.out.println(&quot;수학 점수를 입력해주세요&quot;);
math = scanner.nextInt();
System.out.println(&quot;영어 점수를 입력해주세요&quot;);
en = scanner.nextInt();
if(kor&gt;=40 &amp;&amp; math&gt;= 40 &amp;&amp; en&gt;=40) {

}
else {
System.out.println(&quot;다시입력해주세요&quot;);
state=false;
}
}while(true);
</code></pre>