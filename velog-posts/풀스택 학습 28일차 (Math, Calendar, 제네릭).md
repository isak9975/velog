<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/e03a3f7e-e064-4503-8988-9377f0fcf654/image.jpg" /></p>
<h3 id="stringbuffer-stringbuilder">StringBuffer, StringBuilder</h3>
<hr />
<p>StringBuilder 명령어들은 String 명령어와 다르게 기존 문자열에 영향을 준다.</p>
<p>변경이 자주 일어날경우 Stirng보다 StringBuiler를 사용하는게 좋다.</p>
<blockquote>
</blockquote>
<p>StringBuilder stringBuilder = new StringBuilder(&quot;Hello &quot;);</p>
<ul>
<li><p>append()
기존 문자열의 뒤에 삽입</p>
<pre><code class="language-java">stringBuilder.append(&quot;World&quot;);
System.out.println(&quot;문자열의 길이 : &quot;+stringBuilder.length());</code></pre>
</li>
<li><p>delete()
문자열 삭제</p>
<pre><code class="language-java">stringBuilder.delete(0, 6);</code></pre>
</li>
</ul>
<ul>
<li><p>insert()
원하는 위치에 문자열 삽입</p>
<pre><code class="language-java">stringBuilder.insert(0, &quot;hello &quot;);</code></pre>
</li>
<li><p>reverse()
문자열을 뒤집어서 출력</p>
<pre><code class="language-java">stringBuilder.reverse();</code></pre>
</li>
</ul>
<p><br /><br /><br /></p>
<h3 id="math">Math</h3>
<hr />
<p>수학에서 자주 사용하는 상수들과 함수들을미리 구현해놓은 클래스로 자바에서 수학 계산이 필요할 때 사용한다.
객체를 선언하지 않고 바로 사용할 수 있도록 해당 클래스가 제공하는 모든 메서드는 정적메서드로 이루어져있다.</p>
<ul>
<li><p>ceil()
올림</p>
<pre><code class="language-java">System.out.println(&quot;3.51 올림 : &quot; + Math.ceil(3.51));</code></pre>
</li>
<li><p>floor()
버림</p>
<pre><code class="language-java">System.out.println(&quot;13.61버림 : &quot; + Math.floor(13.61));</code></pre>
</li>
<li><p>rond()
반올림</p>
<pre><code class="language-java">System.out.println(&quot;12.8 반올림 : &quot; + Math.round(12.8));</code></pre>
</li>
<li><p>abs()
절대값구하기</p>
<pre><code class="language-java">System.out.println(&quot;-4.55 절대값 : &quot; + Math.abs(-4.55));</code></pre>
</li>
<li><p>max()
최대값 구하기</p>
<pre><code class="language-java">System.out.println(&quot;30,60 최대값 구하기 : &quot; + Math.max(30, 60));</code></pre>
</li>
</ul>
<ul>
<li>min()
최소값 구하기<pre><code class="language-java">System.out.println(&quot;30,60 최소값 구하기 : &quot;+ Math.min(30, 60));</code></pre>
</li>
</ul>
<ul>
<li><p>pow()
거듭제곱</p>
<pre><code class="language-java">System.out.println(&quot;2의 0제곱 : &quot; + Math.pow(2, 0));
System.out.println(&quot;2의 1제곱 : &quot; + Math.pow(2, 1));
System.out.println(&quot;2의 2제곱 : &quot; + Math.pow(2, 2));
System.out.println(&quot;2의 3제곱 : &quot; + Math.pow(2, 3));</code></pre>
</li>
<li><p>sqrt()
제곱근(루트)</p>
<pre><code class="language-java">System.out.println(&quot;16의 제곱근 : &quot;+Math.sqrt(16));</code></pre>
</li>
<li><p>random()
난수 생성</p>
</li>
</ul>
<p>0.0 이상 1.0 미만의 double 난수</p>
<pre><code class="language-java">  System.out.println(Math.random());
  System.out.println((int)(Math.random()*100));</code></pre>
<ul>
<li>배열에서 최대값 찾기<pre><code class="language-java">int[] numbers = {3,7,11,2,9,4,10,6,14};
int max = 0;
for(int i =0; i &lt; numbers.length;i++) {
max = Math.max(numbers[i], max);
}
System.out.println(max);</code></pre>
</li>
</ul>
<ul>
<li>소수점 첫째자리에서만 반영이 된다.
소수점 둘째자리에서 반올림
곱하기와 나누기로 소수점자리 수 조절해야한다.<pre><code class="language-java">double pi = 3.141592;
double result = Math.round(pi*100.0)/100.0;
System.out.println(result);</code></pre>
</li>
</ul>
<h3 id="wrapper">Wrapper</h3>
<hr />
<p>Wrapper클래스(Wrapper-포장하다)</p>
<p>프로그램에 따라 기본 타입의 데이터를 객체형으로 표시해야하는 경우가 있다.
이를 위해서 자바에서는 기본 자료형을 객체로 다루기 위한 클래스를 제공한다.</p>
<p>이를 Wrapper 클래스라고 부르는데 기본형의 데이터타입을 클래스로 포장했기 때문이다.</p>
<blockquote>
</blockquote>
<p>int -&gt; Integer
char -&gt; Character
float -&gt; Float
double -&gt; Double</p>
<pre><code>생성자를 통한 선언은 JDK1.9부터 사용하지 않는것을 권장

Integer num01 = Integer.valueOf(10);

Double dnum = Double.valueOf(30.11);</code></pre><p><br /><br /><br /></p>
<h3 id="calendar">Calendar</h3>
<hr />
<p>java.util에 있는 날짜와 시간 정보를 제공해주는 클래스
객체를 만들 때 new 키워드를 사용하지 않고 생성된 객체를 받아온다.</p>
<blockquote>
</blockquote>
<p>Calendar cal = new Calendar;
getInstance() 함수를 사용하여 객체를 생성한다.</p>
<p>Calendar calendar = Calendar.getInstance();</p>
<p>int year = calendar.get(Calendar.YEAR);
int month = calendar.get(Calendar.MONTH)+1;
int day = calendar.get(Calendar.DAY_OF_MONTH);
System.out.printf(&quot;오늘 날짜는 %d년 %d월 %d일 입니다.\n&quot;,year,month,day);</p>
<ul>
<li><p>LocalDataTime
날짜 + 시간
java.time 패키지에 있음</p>
<pre><code class="language-java">LocalDateTime now = LocalDateTime.now();
System.out.println(now);</code></pre>
</li>
<li><p>of()
특정 날짜와 시간 만들기</p>
<pre><code class="language-java">LocalDateTime dtime = LocalDateTime.of(2026, 3,21,11,4,11);
System.out.println(&quot;지정한 날짜와 시간 : &quot;+dtime);</code></pre>
</li>
<li><p>날짜/시간 값 얻기</p>
<pre><code class="language-java">System.out.println(&quot;연도 : &quot;+now.getYear());
System.out.println(&quot;월 : &quot; + now.getMonthValue());
System.out.println(&quot;일 : &quot; + now.getDayOfMonth());
System.out.println(&quot;시 : &quot;+ now.getHour());
System.out.println(&quot;분 : &quot;+ now.getMinute());
System.out.println(&quot;초 : &quot;+ now.getSecond());</code></pre>
</li>
<li><p>날짜 /시간 더하고 빼기</p>
<pre><code class="language-java">dtime = LocalDateTime.now();
LocalDateTime tomorrow = dtime.plusDays(1);//+1
LocalDateTime twoHourAgo = dtime.minusHours(2);//-2
System.out.println(&quot;내일 : &quot;+tomorrow);
System.out.println(&quot;2시간 전 &quot; + twoHourAgo);</code></pre>
</li>
<li><p>날짜 /시간 비교</p>
<pre><code class="language-java">LocalDateTime future = dtime.plusDays(1);
System.out.println(&quot;지금이 미래보다 이전인가? &quot; + dtime.isBefore(future));
System.out.println(&quot;지금이 미래보다 후인가? &quot; + dtime.isAfter(future));</code></pre>
</li>
<li><p>자주쓰는 날짜/시간 포맷</p>
<blockquote>
</blockquote>
<p>dtime = LocalDateTime.of(2025, 3,31,14,30);</p>
</li>
</ul>
<p>java.time 패키지에 있는 클래스
날짜나 시간을 문자열로 변경해 줄수 있고
문자열로 된 시간을 날짜/시간 타입으로 변경해 줄수 있다.</p>
<p>포맷(형식만)을 객체형태로 선언
DateTimeFormatter formatter = DateTimeFormatter.ofPattern(&quot;yyy년 MM월 dd일 HH시 mm분&quot;);</p>
<p>날짜를 형식에 맞게 문자열 형태로 변경.
String formatted = dtime.format(formatter);
System.out.println(&quot;포맷된 출력 : &quot; + formatted);</p>
<ul>
<li>자주 쓰는 형식 패턴<blockquote>
</blockquote>
yyyy : 년도(4자리)
yy : 년도(2자리)
MM : 월
dd : 일
HH : 시(24시간)
hh : 시(12시간)
mm : 분
ss : 초
a : 오전/오후
E : 요일 -&gt; Mon,Tue,...
EEEE : 요일(풀네임) -&gt; Monday, Tuesday,...</li>
</ul>
<p><br /><br /><br /></p>
<h3 id="제네릭">제네릭</h3>
<hr />
<p>클래스 내부에서 사용할 데이터 타입을 외부에서 지정하는 기법이다.</p>
<p>객체별로 다른 타입의 자료가 저장될 수 있도록 한다.</p>
<p>클래스나 메서드 내부에 사용될 데이터 타입의 안정성을 높일 수 있다.</p>
<p>제네릭 선언 및 생성</p>
<blockquote>
</blockquote>
<p>public class 클래스명{…}
public interface 인터페이스명{…}</p>
<p>명명하고 싶은대로 아무 단어나 넣어도 문제는 없지만, 대중적으로 통하는 통상적인 네이밍이 있으면 개발이 용이해 지기 때문에 암묵적인 규칙(convention)이 존재한다.</p>
<blockquote>
</blockquote>
<p>type,element,key,value,number</p>
<p><br /><br /></p>
<h4 id="클래스명에도-제네릭이-가능하다">클래스명에도 제네릭이 가능하다.</h4>
<hr />
<p>타입이 들어가는 곳이면 어떤 곳이든 가능한것이 제네릭이다.</p>
<p>객체를 만들때 제네릭의 타입이 결정된다.
한가지의 클래스로 여러가지의 타입을 받을 수 있다.</p>
<p>객체가 만들어지면서 배열을 같이 생성
클래스에 제네릭을 부여하게 되면 해당 클래스를 선언할때
데이터 타입을 부여하게 된다.</p>
<p>제네릭의 타입변수는 기본자료형을 인식하지 않는다.
따라서 int, double 등의 기본자료형을d 제네릭 타입으로 이용하고자 하면
Integer, Double 등의 클래스를 이용해야 한다.
    DataList list = new DataList();</p>
<p><br /><br /></p>
<h4 id="주의점">주의점</h4>
<hr />
<ol>
<li><p>제네릭 타입으로 객체를 생성 할 수 없음.</p>
</li>
<li><p>static 멤버에 제니릭 타입이 올 수 없음</p>
</li>
<li><p>제네릭 클래스 자체를 배열로 만들 수는 없다.</p>
</li>
<li><p>네릭에 들어올 수 있는 타입을 숫자로 제한.
Number의 자식 클래스만 들어와라.</p>
<pre><code class="language-java">class Calculator&lt;T extends Number&gt;{
void add(T a,T b) {};</code></pre>
</li>
</ol>
<p><br /><br /><br /></p>
<h3 id="재네릭-형변환">재네릭 형변환</h3>
<hr />
<p>제네릭 캐스팅 문제</p>
<p>제네릭 서브 타입간에는 형변환이 불가능.</p>
<p>제네릭 타입은 상하관계가 없다.
<br /><br /></p>
<h3 id="컬렉션-프레임">컬렉션 프레임</h3>
<hr />
<ul>
<li><p>List - 순서가 있는 데이터의 집합. 중복허용o</p>
</li>
<li><p>Set - 순서를 유지하지 않는 데이터의, 중복허용x</p>
</li>
<li><p>Map-키와 값의 쌍으로 이루어진 데이터의 집합,</p>
<br />

</li>
</ul>
<h3 id="list컬렉션">List컬렉션</h3>
<hr />
<p>중복이 허용되면서 저장 순서가 유지되는 구조를 제공한다.</p>
<p>List가 제공하는 주요 메서드</p>
<p>void add(E e) = 데이터를 순차적으로 삽입</p>
<p>void add(int index, E e) = 원하는 index 위치에 삽입</p>
<p>void set(int index, E e) = 원하는 index 위치의 값 변경</p>
<p>E get(int index) = 선택된 index 위치의 값 반환</p>
<p>String remove(int index) = 선택된 index위치의 값 삭제하고 value를 반환</p>
<p>void clear() = 모든 데이터 삭제</p>
<p>int size() = 저장된 데이터의 개수 반환</p>
<p>boolean contains(Object o) = 데이터 존재 여부 확인
<br /><br /></p>
<h3 id="arraylist">ArrayList</h3>
<hr />
<p>가장 많이 사용하는 List인터페이스의 대표적인 구현 클래스.</p>
<p>내부적으로 배열을 이용해 구현되어 배열과 호환성이 좋다.</p>
<h4 id="리스트의-선언">리스트의 선언</h4>
<blockquote>
</blockquote>
<p>List list = new ArrayList();</p>
<h4 id="데이터-삽입">데이터 삽입</h4>
<p>list.add(&quot;딸기&quot;);
list.add(&quot;바나나&quot;);
list.add(&quot;망고&quot;);</p>
<h4 id="리스트의-출력">리스트의 출력</h4>
<p>변수명으로 출력했을 때 주소가 아닌 내용이 나온다.
System.out.println(&quot;리스트 내용 : &quot; + list);</p>
<p>리스트의 3번째 위체에 요소 삽입하기
list.add(2,&quot;수박&quot;);
System.out.println(&quot;리스트 내용2 : &quot; + list);</p>
<h4 id="데이터의-변환">데이터의 변환</h4>
<p>list.set(0, &quot;사과&quot;);
list.set(1, &quot;키위&quot;);
System.out.println(&quot;리스트 내용3 : &quot; + list);</p>
<h4 id="데이터의-삭제">데이터의 삭제</h4>
<p>remove(int index) -&gt; 삭제를 하고 삭제한 value를 반환
System.out.println(list.remove(3));
System.out.println(&quot;리스트 내용4 : &quot; + list);</p>
<h4 id="리스트에서-데이터-가져오기">리스트에서 데이터 가져오기</h4>
<p>System.out.println(list.get(1));</p>
<p>리스트에 들어있는 모든 내용 출력하기</p>
<pre><code class="language-java">for(int i =0;i&lt;list.size();i++) {
System.out.print(list.get(i));
}

//향상된 for문을 이용해 출력할 수 있다.

for(String x:list) {
System.out.println(&quot;값 : &quot; + x);
}</code></pre>
<h3 id="linkedlist">LinkedList</h3>
<hr />
<p>데이터와 다음 데이터의 주소를 가지는 노드(Node)객체가 연결되어 데이터를 저장하는 자료구조이다.</p>
<p>ArrayList는 배열을 이용해 데이털를 저장하는 반면, LinkedList는 Node라는 객체를 생성하여 인접 데이터를 링크해서 체인처럼 관리한다.</p>
<h4 id="요소의-추가">요소의 추가</h4>
<p>List의 구현제중 하나이므로 메서드는 동일하다</p>
<pre><code class="language-java">list.add(&quot;Java&quot;);
list.add(&quot;Python&quot;);
list.add(&quot;C++&quot;);</code></pre>
<p>링크드 리스트에는 index가 없지만, 자바에서는 List 인터페이스를
구현하고 있기 때문에 index로 접글할 수 있도록 기능을 제공.</p>
<h4 id="맨-앞뒤에-추가하기">맨 앞/뒤에 추가하기</h4>
<p>list.addFirst(&quot;HTML&quot;);
list.addLast(&quot;JavaScript&quot;);</p>
<p>System.out.println(list);</p>
<h4 id="조회">조회</h4>
<p>System.out.println(list.get(0));</p>