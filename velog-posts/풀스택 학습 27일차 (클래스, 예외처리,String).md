<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/cfab8e06-97a2-4489-80b4-2641843331d9/image.jpg" /></p>
<h3 id="내부-클래스">내부 클래스</h3>
<hr />
<p>클래스안에 만들어진 또 다른 클래스로 중첩 클래스라고도 말한다.</p>
<p>클래스에 다른 클래스를 선언하는 이유는 두개의 클래스가 긴밀한 관계이기 때문이다.</p>
<blockquote>
</blockquote>
<p>public class OuterClass{ //외부 클래스
class InnerClass{ //내부 클래스
}
}</p>
<h4 id="내부-클래스-호출-방법">내부 클래스 호출 방법</h4>
<blockquote>
</blockquote>
<p>Outer outer = new Outer();
Outer.Inner in = new Outer.inner();</p>
<h4 id="내부-클래스의-종류">내부 클래스의 종류</h4>
<pre><code>인스턴스 클래스

정적 클래스

지역 클래스</code></pre><h4 id="장점">장점</h4>
<p>두 클래스 멤버들 간에 손쉽게 접근할수 있다</p>
<p>불필요한 클래스를 감춰서 코드의 복잡성을 줄일 수 있다. </p>
<p><br /><br /><br /></p>
<h3 id="정적-클래스">정적 클래스</h3>
<hr />
<pre><code class="language-java">class PrintOut{
    static class Out{ //이 부분이 정적클래스
        public void println(String str) {
            System.out.println(str);
        }//end method
    }//end out
}//end printout</code></pre>
<h4 id="정적-내부-클래스의-특징">정적 내부 클래스의 특징</h4>
<ol>
<li>외부 클래스의 객체 없이도 사용할 수 있어서 효율적이다.</li>
<li>외부 클래스의 정적 필드와 관련된 클래스를 내부에 묶고 싶을때 적절하다.</li>
<li>캡슐화에 좋다.</li>
</ol>
<p><br /><br /><br /></p>
<h3 id="지역클래스">지역클래스</h3>
<hr />
<pre><code class="language-java">public void processFile(List&lt;String&gt; lines) {
private class InClass{
        public void print() {
            System.out.println(&quot;접근을 pricate으로 제한한다.&quot;);
        }
    }//end InCalss

    public InClass getInClass() {
        return new InClass();
    }//end getInClass()

    public static void main(String[] args) {
        PermitExample permit = new PermitExample();
        //InClass가 pricate이라서 내부 클래스의 객체를
        //wlrwjq aksemf tn djqtek.
        //PermitExample.InClass = permit.new InClass();

        permit.getInClass().print();
    }//end main</code></pre>
<p><br /><br /><br /></p>
<h3 id="익명클래스">익명클래스</h3>
<hr />
<p>익명클래스는 많이 사용된다.</p>
<p>클래스를 확장하기 위해서는 여러가지 클래스를 만들어서 상속을 줘야한다.</p>
<p>하지만 한번만 사용할거라면 익명클래스를 사용해서 간소화 할수 있다.</p>
<p>클래스 내부에서 상속을 간소화하여 사용한다고 이해하면 될 듯 하다.</p>
<pre><code class="language-java">public class PersonMain {
    public static void main(String[] args) {

        Persion persion = new Persion() {
            @Override
            public void mySelf() {
                System.out.println(&quot;저는 회사원입니다&quot;);
            }
        };
        persion.mySelf();

    }//end main
}//end class</code></pre>
<pre><code class="language-java">

    //익명클래스
    //인터페이스 구현을 객체 생성과 동시에 함.
    button.setListner(new ButtonClickListner() {
        @Override
        public void click() {
            System.out.println(&quot;버튼 클릭됨&quot;);

        }
    });
    button.click();
}
</code></pre>
<p>}//end class</p>
<p>//ctrl + shift +p 반대 중괄호로 이동
<br /><br /><br /></p>
<h3 id="예외처리">예외처리</h3>
<hr />
<ul>
<li><p>체크 예외</p>
<p>  Runtime Exception을 제외한 모든 예외</p>
<p>  IOException</p>
<p>  SQLException등</p>
</li>
<li><p>비체크 예외</p>
<p>  Runtime Exception의 자식 클래스 모두 포함</p>
<p>  NullPointerException</p>
</li>
</ul>
<ul>
<li><p>NullPointerException</p>
<p>  생성되지 않은 배열을 출력하려고 할 때 예외 발생</p>
<p>  String[] strArray = null;</p>
<p>  System.out.println(strArray[0]);</p>
</li>
<li><p>NumberFormatException</p>
<p>  잘못된 문자열을 숫자로 형변현할 때 발생</p>
<p>  실수 형태의 문자열을 정수로 변환하게 되면 문제가 발생함.        </p>
<p>  String str02 = &quot;11.2&quot;;
  int num02 = Integer.parseInt(str02);
  System.out.println(&quot;String to int2 : &quot; + num02);</p>
</li>
<li><p>ArrayIndexOutOfBoundsException</p>
<p>  배열에서 인덱스(범위)를 초과해 사용할 때 발생한다.</p>
<pre><code>  int[] arr = {1,6,7,8,10};
  System.out.println(arr[5]);</code></pre></li>
<li><p>ArithmeticException</p>
<p>  정수를 0으로 나누려고 할 때 발생
  코드 문법상 에러는 없음</p>
<pre><code>  int result = 10/0;//코드 문법상 에러는 없음</code></pre></li>
</ul>
<p><br /><br /></p>
<h3 id="try-catch구문">try-catch구문</h3>
<hr />
<ul>
<li>예외를 처리하는 가장 기본 문법</li>
</ul>
<blockquote>
<p>  try {
    //예외가 발생할 수 있는 확률이 있는 코드가 들어감
    } catch (Exception e) {
    //예외가 발생했을 때 어떻게 처리할 거냐
    //예외가 발생한다면 catch문을 거치고 빠져나간다.
    }</p>
</blockquote>
<p>catch()안에 </p>
<p>Exception e -&gt; 하위 예외들에 대한 모든 처리를 할 수 있다.
특정 클래스로 지정해 놓으면-&gt; 해당 예외밖에 처리할 수 없다.
Exception - RuntimeException - InputMismatchException
<br /><br /></p>
<h3 id="다중-catch사용하기">다중 catch사용하기</h3>
<hr />
<p>프로그램을 구동할 때 하나의 예외만 발생한다면 처리하기 어렵지 않다.</p>
<p>하지만 try구문 안에서 다양한 종류의 예외가 발생할 수 있다.
catch구문을 여러개 작성하여 예욉려로 처리 코드를 다르게 작성하여 예외를 처리 할 수 있다.</p>
<pre><code class="language-java">try {
    System.out.println(&quot;몇번째 카드를 뽑으시겠습니까? &gt;&gt;&quot;);
    int num = scanner.nextInt();
    System.out.println(&quot;뽑은 카드 번호는 : &quot; + card[num]);
} catch (IndexOutOfBoundsException e) {
    System.out.println(&quot;해당 번호의 카드는 없습니다&quot;);
}catch (InputMismatchException e) {
    System.out.println(&quot;숫자만 입력해주세요&quot;);
}catch (Exception e) {
    System.out.println(&quot;생각치 못한 에러&quot;);
}</code></pre>
<p><br /><br /><br /></p>
<h3 id="finally">finally</h3>
<hr />
<p>예외 발생 유무와 상관 없이 실행되는 구문이며 생략할 수 있다.
예외를 처리할 때, 예외와 상관없이 반드시 처리해야 하는
구문들을 작성할 때 사용된다.
보통 외부 연동이나 예외가 발생해도 정상 종료되어야 할 구문들에서 사용한다.</p>
<blockquote>
</blockquote>
<p>try{}
catch{}
finally{
연결을 종료하는 코드들
스캐너 연결종료
db와의 연결종료
}</p>
<p><br /><br /><br /></p>
<h3 id="throw">throw</h3>
<hr />
<p>예외던지기
메서드에서 발생한 예외를 직접 처리하는것이 아닌
메서드를 호출한 쪽에서 대신 처리를 해주는것.</p>
<p>강제로 예외 발생</p>
<pre><code>//throw new 예외객체();
throw new Exception(&quot;숫자의 허용범위가 아닙니다.&quot;);
//강제로 예외 발생</code></pre><p><br /><br /><br /></p>
<h3 id="사용자-정의-예외">사용자 정의 예외</h3>
<hr />
<p>Exception 또는 RuntimeException을 상속받아 사용자가 정의한 예외를 만들수 있다.</p>
<p>public class InputErrorException extends Exception{</p>
<pre><code class="language-java">public InputErrorException(String message) {
    super(message);
    }
}</code></pre>
<p><br /><br /><br /></p>
<h4 id="예외-호출법">예외 호출법</h4>
<hr />
<p>if(age&lt;=0) {
throw new InputErrorException(&quot;입력이 잘못되었습니다.&quot;);
}</p>
<p>Throwable</p>
<p>Exception</p>
<p>nullpointer</p>
<p>numberformat</p>
<p>artimetic</p>
<p>arrayIndexoutof</p>
<h3 id="예외던지기">예외던지기</h3>
<hr />
<blockquote>
</blockquote>
<p>throws 예외클래스, 예외클래스</p>
<p>메서드 내부에서 예외를 처리하지 않고, 메서드를 호출한 쪽에서</p>
<p>예외를 처리해주느것</p>
<p>throw → 예외를 강제로 발생시킨다.</p>
<p><br /><br /></p>
<h4 id="기본-api-클래스">기본 API 클래스</h4>
<hr />
<p>라이브러리라고도 한다.</p>
<p>java.lang 패키지</p>
<p>자바 프로그램의 기본적인 클래스를 담고 있는 패키지다.</p>
<p>Object, System, String , StringBuffer/StringBuilder, Math
<br /><br /></p>
<h4 id="object-클래스">Object 클래스</h4>
<hr />
<p>자바의 최상위 클래스</p>
<p>자바에서 생성되는 모든 클래스는 생성될 때 상속을 하지 않아도  Object를 자동으로 상속받게 되어있다.</p>
<pre><code class="language-java">//주소의 비교
System.out.println(&quot;str1 vs str2 : &quot; + (str1==str2));
System.out.println(&quot;str1 vs str3 : &quot; + (str1==str3));

//실제 값에 대한 비교
System.out.println(&quot;str1 vs str2 : &quot;+str1.equals(str2));
System.out.println(&quot;str1 vs str3 : &quot;+str1.equals(str3));</code></pre>
<p>얕은복사(shallow copy)
주소를 복사해주기 때문에 원본값이 바뀌면 복사본도 바뀐다</p>
<pre><code class="language-java">str1 = &quot;bye&quot;;
System.out.println(str1);
System.out.println(str2);
</code></pre>
<p><br /><br /></p>
<h3 id="문자열의-불변immutable">문자열의 불변(immutable)</h3>
<hr />
<p>문자열의 값은 바뀌지 않는다.
문자열을 수정하려고 할때마다 메모리에 항상 새로운 문자열 객체가 생성된다.</p>
<pre><code>int hashCode() 

String toString()</code></pre><p><br /><br /></p>
<h3 id="string-관련-함수들">String 관련 함수들</h3>
<hr />
<ul>
<li>length()
문자열의 길이를 반환하는 메서드<pre><code class="language-java">System.out.println(&quot;문자열 str의 길이 : &quot;+str.length());</code></pre>
</li>
</ul>
<ul>
<li><p>indexOf(char ch)
인자로 전달된 글자의 인덱스 값을 반환한다.
왼쪽부터 오른쪽으로 탐색하고
같은 글자가 여러개 있을 때 가장 먼저 만나는 글자의 index값을 반환</p>
<pre><code class="language-java">System.out.println(&quot;글자 M의 위치 : &quot; + str.indexOf('M'));</code></pre>
</li>
<li><p>charAt(int index)
인자로 전달된 인덱스에 해당하는 글자를 반환</p>
<pre><code class="language-java">System.out.println(&quot;4번 index의 글자 : &quot; + str.charAt(4));</code></pre>
</li>
<li><p>subString(int offset,int end)
일정 인덱스만큼 글자를 잘라서 반환
앞은 이상이고, 뒤는 미만이다</p>
<pre><code class="language-java">System.out.println(str.substring(0,5));

</code></pre>
</li>
</ul>
<ul>
<li>split()
인자로 전달되는 값을 구분자로 문자열을 분할하여 배열형태로 반환<pre><code class="language-java">String[] arr = str.split(&quot; &quot;);</code></pre>
</li>
</ul>
<ul>
<li><p>replace()
특정 문자열을 치환해주는 메서드</p>
<pre><code class="language-java">System.out.println(str.replace(&quot;Mal&quot;, &quot;Gae&quot;));</code></pre>
</li>
<li><p>contains()
특정 문자열을 포함하고 있는지 판별</p>
<pre><code class="language-java">System.out.println(str.contains(&quot;a&quot;));</code></pre>
</li>
<li><p>isEmpty()
문자열의 길이가 0인경우 true를 반환</p>
<pre><code class="language-java">System.out.println(str.isEmpty());</code></pre>
</li>
<li><p>trim()
앞뒤 공백 제거</p>
<pre><code class="language-java">String str2 = &quot;    Hong Gil Dong&quot;   ;
System.out.println(str2.trim());</code></pre>
</li>
<li><p>concat()
두개의 문자열을 이어붙힌다.</p>
<pre><code class="language-java">System.out.println(str.concat(str2));</code></pre>
</li>
<li><p>startWith()
인자로 전달된 문자열로 시작하는지 확인</p>
<pre><code class="language-java">System.out.println(str.startsWith(&quot;Kim&quot;));</code></pre>
</li>
<li><p>endWith(0
인자로 전달된 문자열로 끝나는지 확인</p>
<pre><code class="language-java">System.out.println(str.endsWith(&quot;Ddong&quot;));</code></pre>
</li>
</ul>