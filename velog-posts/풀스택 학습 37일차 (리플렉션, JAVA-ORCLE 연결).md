<p><img alt="" src="https://velog.velcdn.com/images/isak9975/post/39a2bce9-d74c-42d1-aba9-1015c275ff22/image.jpg" /></p>
<h3 id="리플렉션reflection이란">리플렉션(Reflection)이란?</h3>
<hr />
<p>클래스, 메서드, 필드, 생성자 등의 정보를 프로그램 실행 중에 동적으로 조사하거나 조작할 수 있는 기능.</p>
<h4 id="리플렉션-api의-핵심-클래스">리플렉션 API의 핵심 클래스</h4>
<hr />
<ul>
<li>Class&lt;?&gt; - 클래스의 메타 정보를 저장할 수 있는 클래스</li>
<li>Field - 클래스의 필드를 표현</li>
<li>Method - 클래스의 메서드를 표현</li>
<li>Constructor - 생성자를 표현</li>
<li>Annoctation - 어노테이션 정보를 표현</li>
</ul>
<p>User클래스에 대한 정보가 claszz에 담긴다.
필드의 목록, 메서드의 목록 etc...</p>
<pre><code class="language-java">public static void main(String[] args) {
Class&lt;?&gt; claszz = User.class;
    //필드 목록 가져오기
        //필드의 개수
    Field[] filelds = claszz.getDeclaredFields();//모든 필드(private 포함)
    System.out.println(&quot;필드의 개수 : &quot; + filelds.length);

    //필드의 목록을 출력
    //getName() : 필드의 이름을 출력
    //getType() : 필드의 타입을 출력
    for(Field f : filelds) {
        System.out.println(&quot;- &quot;+f.getType()+ &quot;- &quot; + f.getName());

    }

    //메서드 목록 가져오기
    Method[] methods = claszz.getDeclaredMethods();
    for(Method m : methods) {
        String name = m.getName();
        Class&lt;?&gt; returnType = m.getReturnType();
        Parameter[] parameters = m.getParameters();

        System.out.print(&quot;- &quot;+ returnType.getSimpleName() + &quot; &quot; + name + &quot;(&quot; );

        for(Parameter parameter : parameters) {
            System.out.print(parameter.getName());
            System.out.print(&quot;,&quot;);
        }
        System.out.println(&quot;)&quot;);

    }
</code></pre>
<hr />
<p><br /><br /></p>
<h3 id="데이터베이스-연결">데이터베이스 연결</h3>
<hr />
<p>드라이버 =&gt; 두개를 연결해주는 다리</p>
<p>jdbc(java database connectivity)를 사용해서 연결을 했었다.</p>
<blockquote>
</blockquote>
<p>oracle ↔ DBeaver</p>
<p><br /><br /></p>
<h4 id="라이브러리jar">라이브러리(.jar)</h4>
<hr />
<p>다양한 기능을 쉽게 사용할 수 있도록 미리 만들어진 클래스와 메서드의 집합.</p>
<ol>
<li><p>표준 라이브러리</p>
<ul>
<li><p>JDK에 기본적으로 포함되어있음.</p>
</li>
<li><p>java.<em>, java.</em>, javafx.*</p>
</li>
</ul>
</li>
<li><p>외부 라이브러리</p>
<ul>
<li>개발자 별도로 다운로드해서 사용하는 라이브러리</li>
</ul>
</li>
</ol>
<p><br /><br /></p>
<h4 id="statement-보안위험">Statement 보안위험</h4>
<hr />
<pre><code class="language-java">Statement stmt = conn.createStatement();

    String sql = “select * from emp where ename=’”+inputName+”’”;

    ResultSet rs = stmt.excuteQuery(sql)

//‘OR ‘1’ = ‘1 같은 값이 들어가게 되면 전체 테이블이 출력되는 SQL Injection 발생 위험.

//select * from emp where ename=’’ OR ‘1’ = ‘1’</code></pre>