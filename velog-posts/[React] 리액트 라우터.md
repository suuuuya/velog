<h2 id="✅-리액트-라우터란">✅ 리액트 라우터란?</h2>
<blockquote>
<p>리액트 라우터란, <u>리액트 경로에 따라 페이지를 나누도록 해주는 라이브러리</u>로, 컴포넌트를 사용해 페이지를 나누는 것이 일반적이다.</p>
</blockquote>
<br />

<h2 id="✅-라우터">✅ 라우터</h2>
<p>리액트 라우터를 사용하려면 반드시 라우터라는 컴포넌트가 필요하다.
<code>BrowserRouter</code>를 최상위 컴포넌트에서 감싸주면 모든 곳에서 사용할 수 있다.</p>
<pre><code class="language-jsx">import { BrowserRouter } from 'react-router-dom';

function App() {
  return &lt;BrowserRouter&gt; ... &lt;/BrowserRouter&gt;;
}</code></pre>
<br />

<hr />
<br />

<h2 id="✅-페이지-나누기">✅ 페이지 나누기</h2>
<p><code>Routes</code> 컴포넌트 안에다가 <code>Route</code> 컴포넌트를 배치해서 각 페이지를 나눠줄 수 있다.</p>
<p><code>Routes</code> 안에서는 위에서부터 차례대로 <code>Route</code>를 검사하며, 현재 경로와 path prop이 일치하는 <code>Route</code>를 찾는다.</p>
<pre><code class="language-jsx">&lt;Routes&gt;
  &lt;Route path=&quot;/&quot; element={&lt;HomePage /&gt;} /&gt;
  &lt;Route path=&quot;posts&quot; element={&lt;PostListPage /&gt;} /&gt;
  &lt;Route path=&quot;posts/1&quot; element={&lt;PostPage /&gt;} /&gt;
&lt;/Routes&gt;</code></pre>
<br />

<hr />
<br />

<h2 id="✅-링크">✅ 링크</h2>
<p>리액트 라우터에는 a링크 대신 <code>Link</code> 컴포넌트를 사용한다.</p>
<p><code>to</code> prop으로 이동할 경로를 정해준다.</p>
<pre><code class="language-jsx">&lt;Link to=&quot;/posts&quot;&gt;블로그&lt;/Link&gt;</code></pre>
<br />

<hr />
<br />

<h2 id="✅-하위-페이지-나누기">✅ 하위 페이지 나누기</h2>
<p><code>Route</code>안에 <code>Route</code>를 배치한다.
<code>Route</code> 컴포넌트 안에 <code>Route</code>  컴포넌트를 중복해서 사용할 수 있다.</p>
<p><code>index</code>라는 prop을 사용한다.</p>
<pre><code class="language-jsx">&lt;Routes&gt;
  &lt;Route path=&quot;/&quot;&gt;&lt;HomePage /&gt;&lt;/Route&gt;
  &lt;Route path=&quot;posts&quot; element={&lt;PostLayout /&gt;} &gt;
    &lt;Route index element={&lt;PostListPage /&gt;}  /&gt;
    &lt;Route path=&quot;1&quot; element={&lt;PostPage /&gt;}  /&gt;
  &lt;/Route&gt;
&lt;/Routes&gt;</code></pre>
<p>🌠 부모 <code>Route</code>에 element를 지정하고, <code>Outlet</code>이라는 컴포넌트를 활용하면 레이아웃을 지정해줄 수도 있다.</p>
<pre><code class="language-jsx">import { Outlet } from 'react-router-dom';

function PostLayout() {
  return (
    &lt;div&gt;
      &lt;h1&gt;블로그&lt;/h1&gt;
      &lt;hr /&gt;
      &lt;Outlet /&gt;
    &lt;/div&gt;
  );
}

export default PostLayout;</code></pre>
<br />

<hr />
<br />

<h2 id="✅-동적인-경로">✅ 동적인 경로</h2>
<p>콜론(<code>:</code>)으로 시작하는 문자열을 사용하면 경로에 파라미터를 지정할 수 있다.</p>
<p>e.g. </p>
<pre><code class="language-jsx">&lt;Routes&gt;
  &lt;Route path=&quot;/&quot;&gt;&lt;HomePage /&gt;&lt;/Route&gt;
  &lt;Route path=&quot;posts&quot; element={&lt;PostLayout /&gt;} &gt;
    &lt;Route index element={&lt;PostListPage /&gt;}  /&gt;
    // `/posts/:postId/` 경로는
    // `/posts/123`, `/posts/abc`.. 라는 주소로 접속하면
    // 123,abc,... 라는 값을 postId라는 파라미터로 받는다.
    &lt;Route path=&quot;:postId&quot; element={&lt;PostPage /&gt;}  /&gt;
  &lt;/Route&gt;
&lt;/Routes&gt;</code></pre>
<p>경로 파라미터를 사용할 땐, <code>useParams</code>라는 훅을 사용한다.</p>
<pre><code class="language-jsx">function PostPage() {
  const { postId } = useParams();
  // ...
}</code></pre>
<br />

<hr />
<br />

<h2 id="✅-쿼리-사용하기">✅ 쿼리 사용하기</h2>
<pre><code class="language-jsx">import { useSearchParams } from 'react-router-dom';

function PostListPage() {
  const [searchParams, setSearchParams] = useSearchParams();
  const filterQuery = searchParams.get('filter');

  // ...
}</code></pre>
<p>쿼리 값을 변경하고 주소를 이동하고 싶다면 Setter 함수에 객체를 넘겨준다.</p>
<p>객체의 프로퍼티로 쿼리 값을 지정할 수 있다.</p>
<pre><code class="language-jsx">// ?filter=react라는 쿼리로 이동하는 예시
setSearchParams({
  filter: 'react',
});</code></pre>
<br />

<hr />
<br />

<h2 id="✅-페이지-이동하기">✅ 페이지 이동하기</h2>
<h3 id="navigate-컴포넌트">Navigate 컴포넌트</h3>
<p>리턴 값으로 <code>Navigate</code> 컴포넌트를 리턴하면 <code>to</code> prop으로 지정한 경로로 이동한다.</p>
<pre><code class="language-jsx">function PostPage() {
  // ...

  const post = getPost(postId);

  // post가 없는 경우 /posts 페이지로 이동
  if (!post) {
    return &lt;Navigate to=&quot;/posts&quot; /&gt;;
  }

  // ...
}</code></pre>
<h3 id="usenavigate-hook">useNavigate Hook</h3>
<p><code>useNavigate</code> 라는 hook으로 navigate 함수를 가져오면 이 함수를 통해 페이지를 이동할 수 있다.</p>
<pre><code class="language-jsx">const navigate = useNavigate();

const handleClick = () =&gt; {
  // ... 어떤 작업을 한 다음에 페이지를 이동
  navigate('/wishlist');
}</code></pre>
<br />

<hr />
<br />

<h2 id="🌠-link-navigate-usenavigate는-언제-쓰는게-좋을까">🌠 Link, Navigate, useNavigate는 언제 쓰는게 좋을까?</h2>
<h3 id="link">Link</h3>
<blockquote>
<p><strong>사용자가 클릭해서 페이지를 이동하도록 할 때</strong></p>
</blockquote>
<p>☑️ 하이퍼링크 텍스트나 페이지를 이동하는 버튼 등</p>
<pre><code class="language-jsx">// to prop에 이동 경로를 지정
import { Link } from 'react-router-dom';

...
&lt;Link to=&quot;/about&quot;&gt;About&lt;/Link&gt;
...</code></pre>
<br />

<h3 id="navigate">Navigate</h3>
<blockquote>
<p><strong>특정 경로에서 렌더링 시점에 다른 페이지로 이동시키고 싶을 때</strong></p>
</blockquote>
<p>☑️ 쇼핑몰의 회원 전용 페이지에 로그인없이 들어와서 로그인 페이지로 리다이렉트하는 경우
☑️ 쇼핑몰의 상품 상세 페이지에서 제품이 품절되었거나 삭제되어서 다른 페이지로 이동시키는 경우</p>
<pre><code class="language-jsx">// 조건문 안에 Navigate를 사용하면 해당 조건일 때 자동으로 원하는 경로로 이동시킬 수 있다.
import { Navigate } from 'react-router-dom';

function ProfilePage() {
  const isLoggedIn = false;
  if (!isLoggedIn) {
    return &lt;Navigate to=&quot;/login&quot; replace /&gt;;
  }
  ...
}</code></pre>
<br />

<h3 id="usenavigate">useNavigate</h3>
<blockquote>
<p>*<em>특정한 코드의 실행이 끝나고 나서 페이지를 이동시키고 싶을 때
*</em></p>
</blockquote>
<p>☑️ 쇼핑몰에서 장바구니에 담기를 눌렀을 때 리퀘스트를 보내고 장바구니 페이지로 이동시키는 경우
☑️ 쇼핑몰에서 결제하기 버튼을 누르고 나서 모든 결제가 완료된 후에 페이지를 이동시키는 경우
☑️ 리다이렉트된 로그인 페이지에서 로그인을 완료한 후에 처음 진입했던 페이지로 돌아가는 경우</p>
<pre><code class="language-jsx">// 훅을 사용해 navigate 함수를 호출
import { useNavigate } from 'react-router-dom';

function SignupForm() {
  const navigate = useNavigate();
   const handleSubmit = () =&gt; {
    // 회원가입 처리 로직
    ...
    navigate('/home');
  };
  return &lt;button onClick={handleSubmit}&gt;Sign Up&lt;/button&gt;;
}</code></pre>