<p>프로젝트 규모가 커지면, 클래스 네이밍이 점점 복잡해지고, 스타일 충돌이나 유지보수의 어려움도 생긴다.
컴포넌트 중심으로 구조를 설계하면서 SCSS를 함께 사용하기 시작했고, 효율적으로 관리하기 위해 BEM 방식에 따라 클래스 이름을 짓기 시작했다. (물론, 클래스 이름이 길어지면 살짝 번거로운 듯 하지만. . 😅) </p>
<p>BEM 방식 작성은 구조의 일관성과 재사용성으로 인해 관리가 훨씬 쉬워진다!
<br /><br /></p>
<h2 id="✅-bem이란">✅ BEM이란?</h2>
<blockquote>
<p>BEM은 CSS 방법론 중 하나로, <strong>Block, Element, Modifier</strong>를 뜻한다.</p>
</blockquote>
<p>독립적인 컴포넌트 <code>Block</code>과 그 블럭을 구성하는 <code>Element</code>, 그리고 블럭이나 앨리먼트 속성을 담당하는 <code>Modifier</code>. BEM 방식은 HTML 요소들을 이 세 가지로 분류해서 클래스 이름을 짓는 방법을 말한다. </p>
<p>🌠 <strong>BEM 방식 규칙</strong></p>
<ul>
<li>BEM은 기본적으로 ID를 사용하지 않으며, <code>class</code>만을 사용한다.</li>
<li>'어떻게 보이는가'가 아닌, '어떤 목적인가'에 따라 이름을 짓는다.
예를 들어, 어떤 에러 메시지를 띄우는 태그에 .red가 아닌 <code>.error</code>라는 목적에 맞는 이름을 지어줘야한다.</li>
<li>이름을 연결할때는 <code>-</code> 하이픈 하나만 써서 연결한다.</li>
</ul>
<p><br /><br /></p>
<h3 id="block">Block</h3>
<p>BEM의 첫번째 구성 요소 Block.
블럭은 독립적인 기능이나 역할을 가지는 요소를 말한다.
쉽게 말하면, 어딘가에 종속되지 않아서 여기저기 재사용이 가능한 단위를 말한다. </p>
<p>블럭 요소는 블럭을 감쌀 수 있다.</p>
<p>🌠 Block 요소: <code>.header</code>, <code>.nav</code></p>
<pre><code class="language-html">&lt;header class=&quot;header&quot;&gt;
    &lt;nav class=&quot;nav&quot;&gt;
    ...
       &lt;nav&gt;
&lt;/header&gt;</code></pre>
<p>예시로, Search UI 컴포넌트를 가지고 자세히 설명해보겠다.</p>
<p>🌠 Block 요소: <code>.search-form</code></p>
<pre><code class="language-html">&lt;form class=&quot;search-form&quot;&gt;&lt;/form&gt;</code></pre>
<p><br /><br /></p>
<h3 id="element">Element</h3>
<p>엘리먼트는 블럭 내부에 속한 요소로, 블럭의 일부를 구성한다.
블럭이 독립적인 형태라면, 엘리먼트는 의존적인 형태이다. 자신이 속한 블럭 안에서만 의미를 가지기 때문에 블럭 밖으로 꺼내서 다른데 쓸 수 없다.</p>
<p>클래스 네이밍은 <code>&#95;&#95;</code>로 구분 짓는다.
<br /></p>
<p>위에서 설명한 <code>.search-form</code>은 어느 곳에다가 재사용해도 되지만, 
내부의 <code>input</code>과 <code>button</code>은 <code>.search-form</code>을 위한 인풋 창이자 버튼이기 때문에, <code>.search-form</code>에 종속되어야만 의미가 있는 것이다.</p>
<p>🌠 Element 요소: <code>.search-form&#95;&#95;input</code>, <code>.search-form&#95;&#95;button</code></p>
<pre><code class="language-html">&lt;form class=&quot;search-form&quot;&gt;
    &lt;input class=&quot;search-form__input&quot; /&gt;
    &lt;button class=&quot;search-form__button&quot;&gt;Search&lt;/button&gt;
&lt;/form&gt;</code></pre>
<p>또한, 블럭 요소처럼 엘리먼트도 중첩 사용 가능하다.</p>
<p>🌠 Element 요소: <code>.search-form&#95;&#95;content</code>, <code>.search-form&#95;&#95;input</code>, <code>.search-form&#95;&#95;button</code></p>
<pre><code class="language-html">&lt;form class=&quot;search-form&quot;&gt;
  &lt;div class=&quot;search-form__content&quot;&gt;
    &lt;input class=&quot;search-form__input search-form__input--focused&quot; /&gt;
    &lt;button class=&quot;search-form__button&quot;&gt;Search&lt;/button&gt;
  &lt;/div&gt;
&lt;/form&gt;</code></pre>
<p><br /><br /></p>
<h3 id="modifier">Modifier</h3>
<p>모디파이어는 엘리먼트나 블럭의 스타일, 기능을 수정하거나 변형하는 데 사용된다.
클래스 네이밍은 <code>--</code>로 구분 짓는다.</p>
<p><code>--focused</code>가 수식어에 해당한다.
이런식으로 작성된 걸 <code>불리언(boolean)</code> 타입이라고 하는데, 그 값이 true라고 가정하고 사용한다.</p>
<p>🌠 Modifier 요소: <code>.tab__item--focused</code></p>
<pre><code class="language-html">&lt;ul class=&quot;tab&quot;&gt;
    &lt;li class=&quot;tab__item tab__item--focused&quot;&gt;&lt;/li&gt;
    &lt;li class=&quot;tab__item&quot;&gt;탭 02&lt;/li&gt;
    &lt;li class=&quot;tab__item&quot;&gt;탭 03&lt;/li&gt;
&lt;/ul&gt;</code></pre>
<p>그리고, <code>키-밸류(key-value)</code> 타입도 있다. 이건 하이픈으로 성질<code>-</code>내용을 작성한다.
🌠 Modifier 요소: <code>.form-login--theme-normal</code></p>
<pre><code class="language-html">  &lt;form class=&quot;form-login form-login--theme-normal&quot;&gt;
    &lt;input type=&quot;text&quot; class=&quot;form-login__id&quot;/&gt;
    &lt;input type=&quot;password&quot; class=&quot;form-login__password&quot;/&gt;
  &lt;/form&gt;</code></pre>
<p><br /><br /></p>
<h2 id="✅-스타일링">✅ 스타일링</h2>
<p>BEM 방식으로 마크업 구조를 작성하고 SCSS를 사용해 스타일링하면 길게 늘어지는 셀렉팅을 막아주고, 컴포넌트 요소를 쉽게 찾을 수 있다.</p>
<pre><code class="language-html">&lt;form class=&quot;search-form&quot;&gt;
  &lt;div class=&quot;search-form__content&quot;&gt;
    &lt;input class=&quot;search-form__input search-form__input--focused&quot; /&gt;
    &lt;button class=&quot;search-form__button&quot;&gt;Search&lt;/button&gt;
  &lt;/div&gt;
&lt;/form&gt;</code></pre>
<pre><code class="language-scss">// css
.search-form{}
.search-form .search-form__content{}
.search-form .search-form__input{}
.search-form .search-form__input--focused{}
.search-form .search-form__button{}

// scss
.search-form {
  &amp;__input {
    &amp;--focused {
    }
  }
  &amp;__button {
  }
}</code></pre>
<br />


<hr />
<h2 id="참고자료">참고자료</h2>
<p><a href="https://getbem.com/introduction/">https://getbem.com/introduction/</a>
<a href="https://nykim.work/15">https://nykim.work/15</a></p>