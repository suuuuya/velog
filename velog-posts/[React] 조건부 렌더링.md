<h2 id="✅-논리-연산자-활용하기">✅ 논리 연산자 활용하기</h2>
<h3 id="and-연산자">AND 연산자</h3>
<p>show 값이 true 이면 렌더링 하고, false 이면 렌더링 하지 않는다.</p>
<pre><code class="language-js">import { useState } from 'react';

function App() {
  const [show, setShow] = useState(false);

  const handleClick = () =&gt; setShow(!show);

  return (
    &lt;div&gt;
      &lt;button onClick={handleClick}&gt;토글&lt;/button&gt;
      {show &amp;&amp; &lt;p&gt;보인다 👀&lt;/p&gt;}
    &lt;/div&gt;
  );
}

export default App;
</code></pre>
<br />

<h3 id="or-연산자">OR 연산자</h3>
<p>hide 값이 true 이면 렌더링 하지 않고, false 이면 렌더링 한다.</p>
<pre><code class="language-js">import { useState } from 'react';

function App() {
  const [hide, setHide] = useState(true);

  const handleClick = () =&gt; setHide(!hide);

  return (
    &lt;div&gt;
      &lt;button onClick={handleClick}&gt;토글&lt;/button&gt;
      {hide || &lt;p&gt;보인다 👀&lt;/p&gt;}
    &lt;/div&gt;
  );
}

export default App;</code></pre>
<br />

<hr />
<br />

<h2 id="✅-삼항-연산자-활용하기">✅ 삼항 연산자 활용하기</h2>
<p>삼항 연산자를 사용하면 참, 거짓일 경우에 다르게 렌더링해줄 수 있다.</p>
<pre><code class="language-js">import { useState } from 'react';

function App() {
  const [toggle, setToggle] = useState(false);

  const handleClick = () =&gt; setToggle(!toggle);

  return (
    &lt;div&gt;
      &lt;button onClick={handleClick}&gt;토글&lt;/button&gt;
      // toggle 의 값이 참일 경우엔 '✅'을,
      // 거짓일 경우에는 '❎'를 렌더링
      {toggle ? &lt;p&gt;✅&lt;/p&gt; : &lt;p&gt;❎&lt;/p&gt;}
    &lt;/div&gt;
  );
}

export default App;
</code></pre>
<br />

<hr />
<br />

<h2 id="✅-렌더링되지-않는-값들">✅ 렌더링되지 않는 값들</h2>
<p>아래 컴포넌트에서 중괄호 안에 있는 값은 아무것도 렌더링하지 않는다.</p>
<pre><code class="language-js">function App() {
  const nullValue = null;
  const undefinedValue = undefined;
  const trueValue = true;
  const falseValue = false;
  const emptyString = '';
  const emptyArray = [];

  return (
    &lt;div&gt;
      &lt;p&gt;{nullValue}&lt;/p&gt;
      &lt;p&gt;{undefinedValue}&lt;/p&gt;
      &lt;p&gt;{trueValue}&lt;/p&gt;
      &lt;p&gt;{falseValue}&lt;/p&gt;
      &lt;p&gt;{emptyString}&lt;/p&gt;
      &lt;p&gt;{emptyArray}&lt;/p&gt;
    &lt;/div&gt;
  );
}

export default App;
</code></pre>
<p>반면, 이 값들은 각각 숫자 0과 1을 렌더링한다.</p>
<pre><code class="language-js">function App() {
  const zero = 0;
  const one = 1;

  return (
    &lt;div&gt;
      &lt;p&gt;{zero}&lt;/p&gt;
      &lt;p&gt;{one}&lt;/p&gt;
    &lt;/div&gt;
  );
}

export default App;
</code></pre>