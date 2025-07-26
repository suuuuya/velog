<h2 id="✅-사이드-이펙트side-effect란">✅ 사이드 이펙트(Side Effect)란?</h2>
<p>말 그대로 외부에 부수적인 작용을 하는 걸 말한다.
함수 안에서 함수 바깥에 있는 값이나 상태를 변경하는 것.</p>
<blockquote>
<p>리액트에서 사이드 이펙트는 <strong>컴포넌트 내부에서 리액트 외부와 상호작용하는 작업을 말한다.</strong></p>
</blockquote>
<br />

<hr />
<br />

<h2 id="✅-사이드-이펙트와-useeffect">✅ 사이드 이펙트와 useEffect</h2>
<blockquote>
<p><code>useEffect</code> 는 리액트 컴포넌트 함수 안에서 사이드 이펙트를 실행하고 싶을 때 사용하는 함수다.</p>
</blockquote>
<p>☑️ DOM 노드를 직접 변경한다거나
☑️ 브라우저에 데이터를 저장하고
☑️ 네트워크 리퀘스트를 보내는 것과 같은 경우</p>
<p>주로 리액트 외부에 있는 데이터나 상태를 변경할 때 사용한다.</p>
<h4 id="예시">예시</h4>
<h3 id="페이지-정보-변경">페이지 정보 변경</h3>
<pre><code class="language-jsx">useEffect(() =&gt; {
  document.title = title; // 페이지 데이터를 변경
}, [title]);</code></pre>
<br />

<h3 id="네트워크-요청">네트워크 요청</h3>
<pre><code class="language-jsx">useEffect(() =&gt; {
  fetch('https://example.com/data') // 외부로 네트워크 리퀘스트
    .then((response) =&gt; response.json())
    .then((body) =&gt; setData(body));
}, [])</code></pre>
<br />

<h3 id="데이터-저장">데이터 저장</h3>
<pre><code class="language-jsx">useEffect(() =&gt; {
  localStorage.setItem('theme', theme); // 로컬 스토리지에 테마 정보를 저장
}, [theme]);</code></pre>
<p>🌠 <code>localStorage</code> 는 웹 브라우저에서 데이터를 저장할 수 있는 기능이다.
<br /></p>
<h3 id="타이머">타이머</h3>
<pre><code class="language-jsx">useEffect(() =&gt; {
  const timerId = setInterval(() =&gt; {
    setSecond((prevSecond) =&gt; prevSecond + 1);
  }, 1000); // 1초마다 콜백 함수를 실행하는 타이머 시작

  return () =&gt; {
    clearInterval(timerId);
  }
}, []);</code></pre>
<br />

<hr />
<br />

<h2 id="✅-useeffect를-쓰면-좋은-경우">✅ useEffect를 쓰면 좋은 경우</h2>
<p>useEffect 는 쉽게 말해서 '동기화'에 쓰면 유용한 경우가 많은데,</p>
<h4 id="핸들러-함수만-사용한-예시">핸들러 함수만 사용한 예시</h4>
<pre><code class="language-jsx">import { useState } from 'react';

const INITIAL_TITLE = 'Untitled';

function App() {
  const [title, setTitle] = useState(INITIAL_TITLE);

  const handleChange = (e) =&gt; {
    const nextTitle = e.target.value;
    setTitle(nextTitle);
    document.title = nextTitle;
  };

  const handleClearClick = () =&gt; {
    const nextTitle = INITIAL_TITLE;
    setTitle(nextTitle);
    document.title = nextTitle;
  };

  return (
    &lt;div&gt;
      &lt;input value={title} onChange={handleChange} /&gt;
      &lt;button onClick={handleClearClick}&gt;초기화&lt;/button&gt;
    &lt;/div&gt;
  );
}

export default App;</code></pre>
<br />

<h4 id="useeffect를-사용한-예시">useEffect를 사용한 예시</h4>
<pre><code class="language-jsx">import { useEffect, useState } from 'react';

const INITIAL_TITLE = 'Untitled';

function App() {
  const [title, setTitle] = useState(INITIAL_TITLE);

  const handleChange = (e) =&gt; {
    const nextTitle = e.target.value;
    setTitle(nextTitle);
  };

  const handleClearClick = () =&gt; {
    setTitle(INITIAL_TITLE);
  };

  useEffect(() =&gt; {
    document.title = title;
  }, [title]);

  return (
    &lt;div&gt;
      &lt;input value={title} onChange={handleChange} /&gt;
      &lt;button onClick={handleClearClick}&gt;초기화&lt;/button&gt;
    &lt;/div&gt;
  );
}

export default App;</code></pre>
<p><code>useEffect</code> 를 사용한 예시에서는 document를 다루는 사이드 이펙트 부분만 따로 처리하고 있다.</p>
<p>이렇게 사용하면 setTitle 함수를 쓸 때마다 document.title 을 변경하는 코드를 신경 쓰지 않아도 되니까 편리해진다.</p>
<p>그리고, 처음 렌더링 되었을 때 'Untitled'라고 페이지 제목을 변경하는 효과도 낼 수 있다.</p>
<blockquote>
<p>이렇게 <code>useEffect</code>를 사용하면, 반복되는 코드를 줄이고, 동작을 쉽게 예측할 수 있는 코드를 작성할 수 있기 때문에 리액트 안과 밖의 데이터를 일치시키는데 활용하면 좋다.</p>
</blockquote>
<br />

<hr />
<br />

<h2 id="✅-정리-함수-cleanup-function">✅ 정리 함수 (Cleanup Function)</h2>
<blockquote>
<p>정리 함수는 컴포넌트가 화면에서 사라질 때, 혹은 다시 실행되기 전에 사이드 이펙트를 청소 해주는 함수다.</p>
</blockquote>
<p>리액트 컴포넌트는 상태나 UI가 변경되거나 새로 렌더링될 때마다 변경된 내용을 반영하는데, 만약 외부 리소스를 사용하고 있다면, 컴포넌트가 사라질 때 그 리소스들을 정리해주지 않으면 메모리 누수나 불필요한 작업이 계속 실행될 수 있다.</p>
<pre><code class="language-jsx">useEffect(() =&gt; {
  // 사이드 이펙트

  return () =&gt; {
    // 사이드 이펙트에 대한 정리
  }
}, [dep1, dep2, dep3, ...]);</code></pre>
<br />

<h3 id="정리-함수가-실행되는-시점">정리 함수가 실행되는 시점</h3>
<p>콜백을 한 번 실행했으면, 정리 함수도 반드시 한 번 실행(<em>새로운 콜백 함수 호출 전이나 컴포넌트가 사라질 때</em>)된다고 생각하면 된다.</p>
<h4 id="예시-타이머">예시: 타이머</h4>
<pre><code class="language-jsx">import { useEffect, useState } from 'react';

function Timer() {
  const [second, setSecond] = useState(0);

  useEffect(() =&gt; {
    const timerId = setInterval(() =&gt; {
      console.log('타이머 실행중 ... ');
      setSecond((prevSecond) =&gt; prevSecond + 1);
    }, 1000);
    console.log('타이머 시작 🏁');

    return () =&gt; {
      clearInterval(timerId);
      console.log('타이머 멈춤 ✋');
    };
  }, []);

  return &lt;div&gt;{second}&lt;/div&gt;;
}

function App() {
  const [show, setShow] = useState(false);

  const handleShowClick = () =&gt; setShow(true);
  const handleHideClick = () =&gt; setShow(false);

  return (
    &lt;div&gt;
      {show &amp;&amp; &lt;Timer /&gt;}
      &lt;button onClick={handleShowClick}&gt;보이기&lt;/button&gt;
      &lt;button onClick={handleHideClick}&gt;감추기&lt;/button&gt;
    &lt;/div&gt;
  );
}

export default App;</code></pre>
<br />

<hr />
<br />