<blockquote>
<p>리액트에서는 대부분의 요소나 값들을 <code>state</code>로 관리하지만, 가끔은 DOM 요소 자체에 직접 접근해야 할 때가 있다.</p>
</blockquote>
<p>☑️ 인풋에 포커스를 주고 싶을 때
☑️ 파일 인풋을 초기화하고 싶을 때
☑️ 특정 DOM의 높이나 너비를 알고 싶을 때</p>
<p>이럴 때 사용하는게 바로 <code><strong>ref(레퍼런스)</strong></code>다.
<br /><br /></p>
<h2 id="✅-ref-객체-생성">✅ Ref 객체 생성</h2>
<p>useRef 함수로 <code>ref</code> 객체를 만들 수 있다.</p>
<pre><code class="language-jsx">import { useRef } from 'react';

const ref = useRef();</code></pre>
<br />

<hr />
<br />

<h2 id="✅-ref-prop-사용하기">✅ Ref prop 사용하기</h2>
<p><code>ref</code> Prop에다가 앞에서 만든 Ref 객체를 내려준다.</p>
<pre><code class="language-jsx">&lt;div ref={ref}&gt; ... &lt;/div&gt;</code></pre>
<br />

<hr />
<br />

<h2 id="✅-ref-객체에서-dom-노드-참조하기">✅ Ref 객체에서 DOM 노드 참조하기</h2>
<p><code>ref</code> 객체의 current 라는 프로퍼티를 사용하면 DOM 노드름 참조할 수 있다.</p>
<p>🌠 <strong>반드시 current 값이 존재하는지 검사하고 사용!</strong></p>
<pre><code class="language-jsx">const node = ref.current;
if (node) {
  // node 를 사용하는 코드
}
</code></pre>
<br />

<hr />
<br />

<h2 id="✅-활용-예제">✅ 활용 예제</h2>
<h3 id="1-이미지-크기-구하기">1. 이미지 크기 구하기</h3>
<blockquote>
<p>img 노드의 크기를 ref를 활용해 출력해보자.</p>
</blockquote>
<p>이미지 노드에 너비와 높이 속성이 있어, <code>ref</code> 객체의 current로 DOM 노드를 참조해 두 속성 값을 가져올 수 있다.</p>
<pre><code class="language-jsx">import { useRef } from 'react';

function Image({ src }) {
  const imgRef = useRef();

  const handleSizeClick = () =&gt; {
    const imgNode = imgRef.current;
    if (!imgNode) return;

    const { width, height } = imgNode;
    console.log(`${width} x ${height}`);
  };

  return (
    &lt;div&gt;
      &lt;img src={src} ref={imgRef} alt=&quot;크기를 구할 이미지&quot; /&gt;
      &lt;button onClick={handleSizeClick}&gt;크기 구하기&lt;/button&gt;
    &lt;/div&gt;
  );
}</code></pre>
<br />

<h3 id="2-인풋-파일-초기화">2. 인풋 파일 초기화</h3>
<blockquote>
<p>파일 인풋에서 선택한 파일을 제거하도록 만들어보자</p>
</blockquote>
<pre><code class="language-jsx">import { useRef } from 'react';

function FileInput({ name, value, onChange }) {
  // 1. 인풋 노드를 참조할 Ref 객체를 생성하고, useRef() 함수를 사용한다.
  const inputRef = useRef();

  const handleChange = (e) =&gt; {
    const nextValue = e.target.files[0];
    onChange(name, nextValue);
  };

  const handleClearClick = () =&gt; {
    // 3-1. handleClearClick 함수에선 인풋 노드에 해당하는 inputRef.current 값이 있는지 확인하고, 
    const inputNode = inputRef.current;
    if (!inputNode) return;

      // 3-2. DOM 노드의 value 값을 빈 문자열로 변경
    inputNode.value = '';
    // 3-3. onChange 로 상위 컴포넌트에 빈 값으로 변경해주는 것도 잊지 말기
    onChange(name, null);
  };

  return (
    &lt;div&gt;
      // 2. inputRef 객체를 파일 인풋에 ref Prop으로 내려준다.
      &lt;input type=&quot;file&quot; onChange={handleChange} ref={inputRef} /&gt;
      &lt;button type=&quot;button&quot; onClick={handleClearClick}&gt;
        X
      &lt;/button&gt;
    &lt;/div&gt;
  );
}

export default FileInput;</code></pre>