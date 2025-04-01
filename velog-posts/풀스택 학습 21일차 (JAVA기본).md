<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/0c8f18dc-7321-4d03-89cd-9cd09f422b2f/image.jpg" /></p>
<h1 id="자바문법">자바문법</h1>
<hr />
<p>자바에서 문자열은 반드시 &quot;&quot;안에 넣어야 한다.</p>
<p>print() : 출력을 하고 줄을 바꾸지 않는다.</p>
<pre><code class="language-java">System.out.print(&quot;welcome&quot;);
System.out.print(&quot;Java World&quot;);
println() : 출력을 하고 줄을 바꾼다.
System.out.println(&quot;Welocome&quot;);
System.out.println(&quot;Java World&quot;);</code></pre>
<p>printf()
문자역 속에서 다른 타입의 데이터를 같이 출력할 수 있게 해주는 형식
서식문자
%d 정수(10진수)
%o 정수(8진수)
%x 정수(16진수)
%f 실수
%s 문자열
%c 문자형
%b 논리형</p>
<pre><code class="language-java">System.out.printf(&quot;제 이름은 %s이고 나이는 %d살입니다, 키는 %fcm입니다&quot;,&quot;홍길동&quot;,30,182.5);</code></pre>
<p><br /><br /><br /></p>
<h2 id="자료형">자료형</h2>
<hr />
<p>자료형(기본자료형)
자바가 처리할 수 있는 데이터의 종류
논리형 boolean  1bit  true, false
문자형 char     2byte 
정수형 byte         1byte -128<del>127
short    2byte -32,768</del>32,767
int     4byte -21억 ~ 21억
long    8byte -900경 ~ 900경
실수형  float   4byte
double  8byte
<br /><br /><br /></p>
<p>정수형을 쓸 때 주의할점</p>
<hr />
<p>자료형이 표현할 수 있는 범위를 벗어난 데이터를 저장하면
오버플로우가 발생해 전혀 다른 값이 저장될 수 있다.
<br /><br /><br /></p>
<p>오버플로우</p>
<hr />
<p>자료형이 표현할 수 있는 최대 범위보다 큰 수를 저장할시
발생하는 현상으로 잘못된 결과를 얻을 수 있다.
<br /><br /><br /></p>
<p>언더플로우</p>
<hr />
<p>자료형이 표현할 수 있는 최소 범위보다 작 은 수를 저장할 때 발생하는 현상
<br /><br /><br /></p>
<p>문자형과 문자열</p>
<hr />
<p>문자형(char)
한글자 짜리 데이터 ''안에 사용을 한다.
문자열(String)
문자들의 나열 &quot;&quot;안에 사용을 한다
<br /><br /><br /></p>
<p>참조자료형</p>
<hr />
<p>메모리상에 데이터가 저장도니 주소를 저장하기 위한 공간
대표적으로는 문자열을 저장하는 String이 있다
개발자가 직접 만들어 추가할 수 있는 자료형이기 때문에
그 수가 정해져있지 않다.
<br /><br /><br /></p>
<h2 id="변수">변수</h2>
<hr />
<p>프로그램을 만들고 실행하는데 필요한 값들을
메모리에 저장해두고, 필요할 때마다 꺼내서 사용</p>
<p>메모리에 무질서하게 저장되는 것이 아니라, 메모리
규칙속에서 일부 공간을 할당받아야한다.</p>
<p>메모리에 값을 저장하기 위해 할당해 놓은 특정 공간을 
변수라고 한다.
<br /><br /><br /></p>
<ol>
<li>변수의 선언</li>
</ol>
<hr />
<p>변수를 사용하기 위해서는 선언을 우선 해야한다.
자료형 변수명;</p>
<p>변수명 짓는 규칙</p>
<ol>
<li>숫자 특수문자($,_제외)가 첫글자로 올 수 없다.</li>
<li>대소문자 구별한다.</li>
<li>일반적으로 영어소문자로 시작한다.</li>
<li>특수문자가 포함될 수 없다</li>
<li>예약어 금지(if, switch, for, while)</li>
<li>한글은 사용하지 않습니다
<br /><br /><br /></li>
</ol>
<h3 id="변수-표기법">변수 표기법</h3>
<hr />
<p>카멜 표기법
두번째 단어부터 첫글자를 대문자로 표기
userName, homeAddress</p>
<p>스네이크 표기법
모든 단어가 소문자로 시작하고 단어와 단어 사이는
_로 연결하는 방식
user_name, home_address
<br /><br /><br /></p>
<h3 id="형변환">형변환</h3>
<hr />
<p>형 변환(casting)
데이터를 다른 자료형의 데이터로 변환하는 것을 의미한다.
모든 연산은 기본적으로 같은 자료형들끼리만 가능하다.
따라서 서로 다른 자료형의 연산을 수행하기 위해서는
같은 자료형으로 변환해야 한다.</p>
<pre><code>    int num =11;
    double num2 = 3.14;
    double numChange = (double)11;

    System.out.println(&quot;num : &quot;+num);
    System.out.println(&quot;num2 : &quot; + num2);
    System.out.println(&quot;numChange : &quot; + numChange);
    System.out.println((int)1.23);</code></pre><p>형 변환은 숫자를 담을 수 있는 기본 자료형간에만 간으
정수형, 실수형 자료형 뿐만 아니라
문자이면서 동시에 숫자기도한 문자형도 가능하다.</p>
<p>자동형변환(Promotion)</p>
<hr />
<p>서로 다른 자료형간의 대입이나 연산을 할 때 형 변환으로 
자료형을 일치시켜야만 하지만, 다음과 같은 경우 자바의
컴파일러가 자동으로 형 변환을 해주기 때문에 생략이 가능하다.</p>
<p>작은 자료형에서 큰 자료형으로 변환할때
정수형
byte -&gt; short -&gt; int -&gt; long
실수형
float(4바이트) -&gt; double(8바이트)</p>
<ol start="2">
<li>정수형이 실수형으로 바뀔때
int i = 14;
double d = 3.14;
d = i ; //자동형변환(int -&gt; double)</li>
</ol>
<p>char c = 'a';
i = c; //char형에서 int형으로 자동 형변환
System.out.println(&quot;i : &quot; + i); //94</p>
<p>강제형변환(Demotion)
(원하는 자료형)데이터 or 변수;</p>
<p>큰쪽에서 작은쪽으로 바꿀때 강제로 바꿔야 한다.</p>
<p>int x = 10;//4byte
byte y = (byte)i; //1byte 큰쪽 =&gt; 작은쪽
System.out.println(x);</p>
<p>//int -&gt; byte 강제 형변환(값이 큰 경우)
int j = 1000;
byte k = (byte)j;</p>
<h2 id="연산자">연산자</h2>
<hr />
<ol>
<li>단항 연산자
항이 한개인 연산자</li>
</ol>
<p>부호연산자</p>
<hr />
<p>int x = 100;
int resultPlus = +x;
int resultMinus = -x;
System.out.println(resultPlus);
System.out.println(resultMinus);
<br /><br /><br /></p>
<ol start="2">
<li>증감연산자</li>
</ol>
<hr />
<p>1씩 증가시키거나 1씩 감소시키는 연산자</p>
<ul>
<li><p>선행증감
1이 먼저 증감되고 코드에 즉시 반영이 된다.</p>
<pre><code class="language-java">int a= 10;
System.out.println(&quot;a : &quot; + ++a);</code></pre>
</li>
<li><p>후행증감
코드가 먼저 실행되고 1일 증가하게 된다.</p>
<pre><code class="language-java">System.out.println(&quot;a : &quot; + a--);
System.out.println(&quot;[RE] a : &quot;+ a);

char alphabetA = 'A'; // 아스키코드값이 65
System.out.println(alphabetA++);//65(+1)
System.out.println(alphabetA);;//66</code></pre>
<p><br /><br /><br /></p>
</li>
</ul>
<p>오버플로우와 언더플로우</p>
<hr />
<p>byte value = 127;
value++;
System.out.println(value);
//오버플로우가 일어나면 최소값으로 바뀐다.</p>
<p>byte value2 = -128;
value2--;
언더플로우가 일어나면 최대값으로 바뀐다.
System.out.println(value2);
언더플로우가 일어나면 최대값으로 바뀐다</p>
<p><br /><br /><br />
논리 부정연산자</p>
<hr />
<p><strong>!</strong>
논리형 값을 가지는 피연산자 !를 붙여서
값을 반대로 바꾸는 역활
연산자를 사용한 곳에서만 적용이 될 뿐 진짜 변수의
값이 바뀌어 저장되는 것은 아니다.</p>
<pre><code class="language-java">boolean isHuman = false;
System.out.println(!isHuman);
System.out.println(isHuman);</code></pre>
<p><br /><br /></p>
<p>이항연산자</p>
<hr />
<pre><code>    피연산자가 2개인 연산자</code></pre><p><br /><br /></p>
<p>산술연산자</p>
<hr />
<pre><code>    int x = 100;
    int y = 200;

    System.out.println(x+y); // 300
    System.out.println(x-y); // -100
    System.out.println(x*y); // 20000
    System.out.println(x/y); // 몫만 나옴
    System.out.println(x%y); // 나머지만 나옴</code></pre><p><br /><br /></p>
<p>오버플로우 발생</p>
<hr />
<pre><code class="language-java">        int result = 10000000 * 1000000;
        System.out.println(result);</code></pre>
<p><br /><br /></p>
<p>산술 변환</p>
<hr />
<p>기본적으로 이항 연산자의 연산은 두 피연산자의
타입이 일치해야 연산이 가능하다.</p>
<p>컴퓨터는 서로 다른 타입을 계산하지 못하므로 값의
손실이 적은쪽으로 타입을 맞춰준다.</p>
<pre><code>long + int -&gt; long + long -&gt; long
float + int =&gt; float + float =&gt; float
double  + float =&gt; double + double =&gt; double</code></pre><p>복합대입연산자</p>
<hr />
<p>산술 연산자와 대입연산자가 합쳐진 형태</p>
<blockquote>
<p>a = a +,-,*,/,%, </p>
</blockquote>
<pre><code class="language-java">        x =10;
        y = 1;

        y += x; // y = y+x;
        System.out.println(y);

        y*= x; // y = y*x;
        System.out.println(y);

        //++x -&gt; x += 1</code></pre>
<p><br /><br /><br /></p>
<p>비교연산자</p>
<hr />
<p>변수나 상수의 값을 비교하여 참과 거짓을 판단하는 연사자.
결과가 항상 <strong>true</strong> 나 <strong>false</strong> 로 반환된다.</p>
<pre><code class="language-java">        int a= 10;
        int b = 20;

        System.out.println(a&gt;b);
        System.out.println(a&lt;=b);
        System.out.println(a==b);//같다
        System.out.println(a!=b);//같지않다</code></pre>
<p><br /><br /><br />        </p>
<p>논리연산자</p>
<hr />
<ul>
<li>&amp;&amp;(and) : 앞 뒤 피연산자가 둘다 참이어야 참을 반환한다.</li>
<li>||(or) : 앞 뒤 피연자 중 하나라도 참이면 참을 반환<pre><code class="language-java">      int myAge = 30;
      int limit = 35;
      boolean res = (limit-myAge) &gt;=5 &amp;&amp; myAge&gt;30;
      System.out.println(&quot;&amp;&amp;연산결과 : &quot; + res);
      res = (limit-myAge) &gt;=5 || myAge&gt;30;
      System.out.println(&quot;||연산결과 : &quot; + res);</code></pre>
<br /><br /></li>
</ul>
<p>비트연산자</p>
<hr />
<p>논리 연산자와 유사하지만 bit 단위의 연산만 가능하다</p>
<ul>
<li>&amp; 논리곱(and) 두 항이 모두 참이면 참 아니면 거짓</li>
<li>| 논리합(or) 두 항 중 하나라도 참이면 참 아니면 거짓</li>
<li>^ 배타적논리합(xor) 두 항이 다르면 참 같으면 거짓</li>
<li>~ 부정(not) 참을 거짓으로 거짓을 참으로 연산</li>
</ul>