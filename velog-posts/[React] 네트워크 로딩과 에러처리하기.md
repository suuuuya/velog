<h4 id="1">1.</h4>
<p>우선 로딩 상태를 다룰 <code>isLoading</code>이라는 스테이트와
에러 객체를 값으로 할 <code>loadingError</code>라는 스테이트를 만든다.</p>
<pre><code class="language-js">const [isLoading, setIsLoading] = useState(false);
const [loadingError, setLoadingError] = useState(null);</code></pre>
<br />

<h4 id="2">2.</h4>
<p><code>try</code> 블록에서 에러 스테이트를 초기화하고, 로딩 스테이트는 true 로 만든다.</p>
<p>만약 에러가 발생한다면 <code>catch</code> 블록에서 에러 스테이트를 변경하고 함수 실행을 끝내기 위해서 리턴한다.</p>
<p><code>finally</code> 블록에서는 다시 로딩 스테이트를 false 로 만들어, <code>catch</code> 블록에서 함수가 종료 되었을 때도 로딩 스테이트가 false 로 변경되게한다.</p>
<pre><code class="language-js">// 예제
const handleLoad = async (options) =&gt; {
  let result;
  try {
    setLoadingError(null);
    setIsLoading(true);
  } catch (error) {
    setLoadingError(error);
    return;
  } finally {
    setIsLoading(false);
  }

  ....
};
</code></pre>
<h4 id="3">3.</h4>
<p>마지막으로 <code>isLoading</code> 스테이트와 <code>loadingError</code> 스테이트를 렌더링에 적용하기.</p>
<p>disabled 속성으로 <code>isLoading</code> 값을 넘겨주고, 조건부 렌더링을 사용해서 <code>loadingError.message</code> 값이 있을 때만 메시지를 보여 주도록 한다.</p>
<pre><code class="language-js">return(
  {cursor &amp;&amp; (
    &lt;button disabled={isLoading} onClick={handleLoadMore}&gt;
      더보기
    &lt;/button&gt;
  )}
  {loadingError?.message &amp;&amp; &lt;p&gt;{loadingError.message}&lt;/p&gt;}
)
</code></pre>