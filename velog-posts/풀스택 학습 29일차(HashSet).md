<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/d4b37927-136d-451b-80e5-e2fa6c1d4ad8/image.png" /></p>
<h3 id="hashset">HashSet</h3>
<hr />
<p>선언방법</p>
<blockquote>
</blockquote>
<p>HashSet hs1 = new HashSet&lt;&gt;();</p>
<ul>
<li>add(E e)
데이터에 추가<pre><code class="language-java">hs1.add(&quot;Orange&quot;);
hs1.add(&quot;apple&quot;);//중복되는 데이터는 추가되지 않는다.
</code></pre>
</li>
</ul>
<p>hs1.add(null); //nu;;도 1번 저장이 가능하다.</p>
<p>System.out.println(hs1);//입력순서대로 출력되지는 않는다.</p>
<pre><code>
- size()
들어있는 요소의 개수
  ```java
  System.out.println(hs1.size());</code></pre><ul>
<li>contains(Object o)
요소가 포함되어 있는지 판별<pre><code class="language-java">System.out.println(hs1.contains(&quot;banana&quot;));</code></pre>
<br />
#### HashSet이 중복되는 요소를 어떻게 체크할까?</li>
</ul>
<ol>
<li>hashcode()로 같은 주소를 가지고 있는지 비교</li>
<li>해시값이 같으면 equals()로 실제값을 비교
둘다 같으면 삭제<br />
#### HasSet을 언제쓰면 좋을까</li>
<li>중복되는 데이터가 없이 뽑을 때</li>
<li>순서나 정렬이 중요하지 않을 때</li>
</ol>
<p><br /><br /></p>
<h3 id="hashset-예시">HashSet 예시</h3>
<hr />
<p>HashSet 객체를 이용하여 로또번호 뽑기</p>
<pre><code class="language-java">HashSet&lt;Integer&gt; hs2 = new HashSet&lt;Integer&gt;();

//1~45 사이의 난수 6개 뽑기

    while (hs2.size()!=6) {
        int r = new Random().nextInt(45)+1;
    hs2.add(r);
}
System.out.println(hs2);

//인덱스가 없기 때문에 하나만 고를 수가 없다.

//HashSet을 배열 형태로 변환


Object[] arr = hs2.toArray();
형변화이 필요하다 -&gt; 타입안정성이 떨어진다


Integer[] arr = hs2.toArray(new Integer[0]);

//왜 Integer에 0을 사용하는 것인가.
//적절한 크기의 새 배열을 만들어서 반환을 해준다.


반복자라고도 불리는 iterator객체
public static void main(String[] args) {
List&lt;Integer&gt; list = Arrays.asList(1,2,3,4,5,6,7,8,9,10);
반환형이 List라서 위 상황처럼 만들수 있는것이다.


Iterator&lt;Integer&gt; iter = list.iterator();

Iterator 메서드
boolean hasNext()
다음값이 있으면 true, 없으면 false
E next()
다음값을 반환

    while(iter.hasNext()) {//
        int val = iter.next();
        System.out.println(val);
    }
</code></pre>
<p>//==================================================================================</p>
<pre><code class="language-java">Set&lt;Integer&gt; set = new HashSet&lt;Integer&gt;();


for(int i =0; i&lt;=10;i++) {
    set.add(i);
    }

    Iterator&lt;Integer&gt; iter2 = set.iterator();

    while(iter2.hasNext()) {
        int val = iter2.next();
        System.out.println(val);
    }</code></pre>
<p>//Iterable(Iterator) -&gt; Collection -&gt; List
//                                      -&gt; Set
이런식의 상속 구조로 List와 Set이 Iterator를 사용할 수 있다.</p>