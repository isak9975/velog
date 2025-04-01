<p><a href="https://velog.velcdn.com/images/isak9975/post/e3012bbf-8d89-47bf-bb1d-ae65c883504e/image.jpg"></a></p>
<h2 id="기타제어문">기타제어문</h2>
<p>반복문은 각각 정해진 횟수 또는 조건에 의해 반복을 진행한다.
하지만 숫자가 표시된 100개의 공에서 특정 숫자가 적힌 공을
찾는데, 10만에 찾았다면 더이상 반복을 할 필요가 없다.
기타 제어문은 반복문의 횟수도 제어할 수 있다. 
<br /><br /><br /></p>
<h3 id="1-continue">1. continue</h3>
<hr />
<p>반복문 안에서 continue 를 만나게 되면 이후의 실행 코드는
수행되지 않고, 반복문의 처음으로 돌아가 반복문을
진행하게 된다.</p>
<p>for 문은 증감식으로 이동하며, while 문고 do-while 문의 경우
조건식으로 이동한다.</p>
<pre><code class="language-java">int sum = 0;
    for(int i =0; i&lt;10; i++) {
        if(i%2==0) {
            continue; //짝수는 건너뛰기.
        }
    sum+=i;
    }
System.out.println(&quot;홀수의 합 : &quot;+sum);</code></pre>
<p><br /><br /><br /></p>
<h3 id="2-break">2. break</h3>
<hr />
<p>break 문은 switch 를 할때 나왔던 구문으로 case 를 종료할 때 사용.
반복문이 진행되는 도중, 특정 조건을 만족해  더이상 반복문을 실행할 필요없이 종료하려고
할 때 사용한다.</p>
<pre><code>break, continue 와 같은 기타제어문들은
반복문 안에서만 사용할 수 있다.</code></pre><pre><code class="language-java">int s= 0;
    while(s&lt;10) {
        if(s==5) {
            break; //s=5일때 더 이상 반복안하고 빠져나오기.
        }
        System.out.println(s+&quot; &quot;);
        s++;
    }
System.out.println();</code></pre>
<p><br /><br /><br /></p>
<h3 id="3-label">3. label</h3>
<hr />
<p>기타제어문을 포함하고 있는 반복문에 대해서만 영향이 있다.
라벨링을 하면 내가 원하는 반복문에 대해서 조작을 할 수 있다.
라벨은 항상 쌍으로 존재한다.</p>
<pre><code class="language-java">out:for(int i=0;i&lt;3;i++) {
for(int j =0;j&lt;=10;j++) {
    if(j%2==0) {
        break out;
                }System.out.println(j+&quot; &quot;);
            }
            System.out.println();
        }</code></pre>
<p><br /><br /><br />      </p>
<h2 id="배열">배열</h2>
<hr />
<blockquote>
</blockquote>
<pre><code>String[] array1 = null;
String array2[] = null;</code></pre><p>대괄호[]는 배열의 연산자를 의미
자료형 뒤에 붙이거나 변수명 뒤에 붙이면 해당 자료형은 배열이라는 의미로 선언된다.
자료형 뒤에 붙이는 것이 가독성이 좋아 자주 사용된다
프로그래밍에서는 뭔가를 기억할 때 메모리를 사용한다.
생성하기 위해서는 <strong>'new'</strong> 키워드를 사용해야함. 
메모리의 공간 확보 </p>
<pre><code class="language-java">   int [] arr;//배열선언
        arr = new int[] {
                1,2,3,4,5 // 배열 재정의
        };</code></pre>
<pre><code>값을 직접 변수에 저장하는것이 아니라 주소값이 저장되어
해당 주소를 통해 실제 주소에 접근하는 것을 참조변수라고 한다.

배열의 특징
    1. 배열 선언 시 크기를 지정한다.
    2. 배열 선언 후 공간의 크기를 늘리거나 줄일수 없다
    3. 지정된 자료형의 값만 저장할 수 있다.

    배열에 각 방에 들어있는 데이터를 사용하는법
    배열명[index] -&gt; 변수처럼 사용하면 된다.
    대입이 가능하다.</code></pre><pre><code class="language-java">        iArr[0] = 100;
        iArr[1] = 200;
        iArr[2] = 300;
        iArr[3] = 400;</code></pre>
<pre><code>배열의 길이
    배열은 내부적으로 length 라는 변수를 지니는데, 
    해당 변수는 배열의 길이 값을 가지고 있다
    배열 길이 알고싶을 때는 배열명.length 를 하면 된다.
    이 변수의 값은 배열이 생성될 때 지정되며 변결 할 수 없다.


배열의 초기값
    배열은 생성과 동시에 데이터 자료형별로 기본값이 주어진다.
    정수 -&gt; 0
    실수 -&gt; 0.0
    문자형 -&gt; ''
    객체형 -&gt; null</code></pre><p><br /><br /><br /></p>
<h4 id="null">null</h4>
<hr />
<pre><code>    변수를 만들때 초기활르 하지 않으면 자료형에 맞는 아무값이(쓰레기값) 들어간다.
    배열을 선언만 하고 생성하지 않을 경우, 시스템은 배열을 만들때 null 이라는 키워드를 부여한다.
    null 의 의미는 없다 라는 의미를 가진다.</code></pre><p><br /><br /><br />        </p>
<h2 id="arrays">Arrays</h2>
<hr />
<p>Arrays 클래스는 배열의 복사, 항목의 정렬, 항목 검색
배열을 다루기 위한 다양한 메서드를 제공한다
Arrays 클래스를 이용하면 배열의 기능을 더욱 쉽게 사용할수 있다.</p>
<p>Scanner,Random 클래스의 경우
객체를 먼저 생성을 하고 메서드를 사용함</p>
<p>Arrays.함수명()으로 작성하여 기능을 호출한다.
<br /><br /><br /></p>
<h3 id="1-배열의-출력">1. 배열의 출력</h3>
<hr />
<blockquote>
</blockquote>
<p><strong>toString()</strong>
반복문의 도움 없이 배열을 출력할 수 있도록 도와준다.
배열에 정의된 값을 문자열 형태로 변환하여 출력해준다.</p>
<pre><code class="language-java">int[] arr = {1,6,2,3,10,7,4,5,8,9};
System.out.println(Arrays.toString(arr));</code></pre>
<br />

<ol start="2">
<li>배열의 정렬</li>
</ol>
<hr />
<blockquote>
</blockquote>
<p><strong>sort()</strong>
기본적으로 오름차순으로 정렬해준다.</p>
<pre><code class="language-java">System.out.println(&quot;정렬 전&quot;);
System.out.println(Arrays.toString(arr));
Arrays.sort(arr); // 반환값이 없음.
System.out.println(&quot;정렬 후&quot;);
System.out.println(Arrays.toString(arr));</code></pre>
<p>Comparator.reverseOrder()를 통해 내림차순으로 정렬이 가능하다.
하지만 기본자료형 배열로는 불가능하다.
기본자료형의 클래스타입인 Wrapper 클래스를 이용한다.</p>
<p>Comparator.reverseOrder()를 통해 내림차순으로 정렬이 가능하다.
하지만 기본자료형 배열로는 불가능하다.
기본자료형의 클래스타입인 Wrapper 클래스를 이용한다.</p>
<pre><code class="language-java">Integer[] iArrIntegers = {1,6,2,3,10,7,4,5,8,9};

Arrays.sort(iArrIntegers,Comparator.reverseOrder());
System.out.println(Arrays.toString(iArrIntegers));</code></pre>
<br />        

<p>배열의 복사
자바에서 배열은 한 번 생성하면 그 길이를 변경할 수 없다.
따라서 더 많은 데이터를 저장하거나 기존의 배열과 똑같은
배열을 새로 만드려면 배열을 복사해야한다.
배열을 복사하는 방법에는 얕은 복사와 깊은 복사 두가지가 있다.</p>
<p><strong>얕은 복사(Shallow Copy)</strong> : 복사된 배열이나 원본 배열이
서로 간의 값이 함께 변경된다.</p>
<p><strong>깊은 복사(Deep Copy)</strong> : 복사된 배열이나 원본 배열이
변경될 때 서로 간의 값은 바뀌지 않는다.</p>
<pre><code class="language-java">int[] arr01 = {1,2,3};
arr01은 배열 {1,2,3}의 주소값을 가지고 있다.
System.out.println(arr01);</code></pre>
<pre><code class="language-java">int[] arr02 = arr01; //얕은 복사

//배열 arr02의 값변경 // 얕은 복사는 같이 변경됨(주소값의 복제)
arr02[1] = 10;
System.out.println(&quot;arr01 배열 : &quot; + Arrays.toString(arr01));
System.out.println(&quot;arr01 배열 : &quot; + Arrays.toString(arr02));</code></pre>
<p><br /><br />        </p>
<h3 id="깊은-복사">깊은 복사</h3>
<hr />
<p>배열의 깊은 복사는 반복문을 이용해 새로운 배열에 값을
직접 넣어주거나 Arrays 클래스 또는 System 클래스가 가진 기능을 이용한다.</p>
<p>int cards[] = {1,6,4,5,3,2};
int[] newCards = new int [cards.length];</p>
<ol>
<li>Arrays 클래스를 이용한 깊은 복사<blockquote>
</blockquote>
int[] newCards2 = Arrays.copyOf(cards,cards.length);<br /></li>
<li>반복문을 이용한 깊은 복사<blockquote>
</blockquote>
for(int i =0; i&lt;cards.length;i++) {
newCards[i]= cards[i]; 
}<br /></li>
<li>System 클래스를 이용한 깊은 복사<blockquote>
</blockquote>
int[] newCards3 = new int[cards.length];
System.arraycopy(cards,0,newCards3,0,cards.length);</li>
</ol>
<h3 id="다차원배열">다차원배열</h3>
<hr />
<p>2차원 이상의 배열을 의미하며, 비열의 요소로 또 다른 배열을 가지는것을 의미한다.
2차원 배열은 요소로서 1차원 배열을 가진다.        </p>
<blockquote>
</blockquote>
<p>int[][] arr = new int[2차원 배열의 크기][1차원 배열의 크기];</p>
<pre><code class="language-java">int[][] arr2 = {{1,2,3},{4,5,6},{7,8,9}};
    System.out.println(arr2[0][0]);

//요소로 들어가는 1차원 배열의 크기를 지정하지 않고 생성할 수 있다.
    int[][] arr3 = new int[3][];

//각 배열의 크기를 각각 선언하여 사용할 수 있다.
    int[][] arr4 = new int[3][2];
</code></pre>
<pre><code class="language-java">int[][] iArr = new int[2][3];

        iArr[0][0] = 1;
        iArr[0][1] = 2;
        iArr[0][2] = 3;
        iArr[1][0] = 5;
        iArr[1][1] = 6;</code></pre>