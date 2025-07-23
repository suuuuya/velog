<p>이번 포스팅에서는, 여러 메소드를 사용해 다양한 기능을 만드는 내용 위주로 정리했다. 🧑🏻‍🦲
<br /><br /></p>
<h2 id="✅-map">✅ map</h2>
<h3 id="🔎-map으로-렌더링하기">🔎 map으로 렌더링하기</h3>
<p>배열을 렌더링할 때는 <code>map</code>메소드를 사용한다.</p>
<blockquote>
<p>리액트는 UI를 구성할 때, 배열 데이터를 화면에 반복해서 보여줄 일이 많기 때문에, 이럴 때 <code>map()</code>을 사용해서 배열의 각 아이템을 JSX로 바꿔서 화면에 렌더링한다.</p>
</blockquote>
<pre><code class="language-js">function List({ items = [] }) {
  return (
    &lt;ul&gt;
      {items.map((item) =&gt; (
        &lt;li key={item.id}&gt;{item.title}&lt;/li&gt;
      ))}
    &lt;/ul&gt;
  );
}</code></pre>
<br />

<hr />
<br />

<h2 id="✅-key">✅ key</h2>
<blockquote>
<p>각 요소를 렌더링 할 때는 <code>key</code> Prop을 내려줘야한다.
배열을 렌더링할 때 최상위 태그에다가 지정해 주면 된다.</p>
</blockquote>
<h4 id="📚-예제에-사용해보기">📚 예제에 사용해보기</h4>
<p>id는 각 요소를 구분할 수 있는 고유한 값이기 때문에 사용한 것이고, 
<u>반드시 id 일 필요없이 데이터를 구분할 수 있는 고유의 값이면 무엇이든 <code>key</code>가 된다.</u></p>
<pre><code class="language-js">function MovieList({ items, onDelete }) {
  return (
    &lt;ul className=&quot;MovieList&quot;&gt;
      {items.map((item) =&gt; (
        &lt;li key={item.id}&gt;
          &lt;MovieListItem item={item} onDelete={onDelete} /&gt;
        &lt;/li&gt;
      ))}
    &lt;/ul&gt;
  );
}
</code></pre>
<br />

<hr />
<br />

<h2 id="✅-sort">✅ sort</h2>
<br />

<h3 id="🔎-sort로-정렬-하기바꾸기">🔎 sort로 정렬 하기/바꾸기</h3>
<blockquote>
<p><code>sort()</code> 메소드를 활용해서 <strong>최신순/베스트순</strong> 정렬 기능을 만들어보자</p>
</blockquote>
<br />

<h4 id="📚-기능">📚 기능</h4>
<p>☑️ 처음 페이지가 열렸을 때, 기본 정렬 <code>최신순</code>
☑️ <code>최신순</code> 버튼 클릭 시, 생성일이 가까운 순서대로 정렬
☑️ <code>베스트순</code> 버튼 클릭 시, 별점이 높은 순서대로 정렬</p>
<br />

<h4 id="📚-메소드-활용">📚 메소드 활용</h4>
<p>🌠** <code>sort()</code> 메소드는 <u>아규먼트로 콜백 함수를 받는데, 이 함수에서 두 요소끼리 비교</u>를 하게 된다.**
<br /></p>
<p>이 콜백의 파라미터를 a, b라고 했을 때,</p>
<ul>
<li>작은 순서대로 정렬: <code>numbers.sort((a, b) => a - b)</code></li>
<li>크기가 큰 순서대로 정렬: <code>numbers.sort((a, b) => b - a)</code></li>
</ul>
<pre><code class="language-js">// 생성일이 가까운 순
items.sort((a, b) =&gt; b.createdAt - a.createdAt)
// 별점이 높은 순
items.sort((a, b) =&gt; b.rating - a.rating)</code></pre>
<p>위처럼 쓸 수 있겠다.</p>
<br />

<h4 id="📚-각-버튼-생성">📚 각 버튼 생성</h4>
<pre><code class="language-js">const [order, setOrder] = useState('createdAt');</code></pre>
<p>정렬 기준이 되는 프로퍼티를 order 라는 스테이트로 두고 변경하도록 만들자.
<br /></p>
<pre><code class="language-js">const handleNewestClick = () =&gt; setOrder('createdAt');
const handleBestClick = () =&gt; setOrder('rating');

// ...
// 각 함수를 각각 버튼에 onClick 핸들러로 추가
&lt;button onClick={handleNewestClick}&gt;최신순&lt;/button&gt;
&lt;button onClick={handleBestClick}&gt;베스트순&lt;/button&gt;
</code></pre>
<p>그리고 나서 버튼이 클릭될 때마다 order 스테이트 값을 바꿔줄 수 있도록 하자.
<br /></p>
<h4 id="📚-결과">📚 결과</h4>
<h4 id="📄-appjs">📄 App.js</h4>
<pre><code class="language-js">import { useState } from 'react';
import MovieList from './MovieList';
import items from '../mock.json';

function App() {
  const [order, setOrder] = useState('createdAt');

  const handleNewestClick = () =&gt; setOrder('createdAt');
  const handleBestClick = () =&gt; setOrder('rating');

  const sortedItems = items.sort((a, b) =&gt; b[order] - a[order]);

  return (
    &lt;div&gt;
      &lt;button onClick={handleNewestClick}&gt;최신순&lt;/button&gt;
      &lt;button onClick={handleBestClick}&gt;베스트순&lt;/button&gt;
      &lt;MovieList items={sortedItems} /&gt;
    &lt;/div&gt;
  );
}

export default App;</code></pre>
<br />

<hr />
<br />

<h2 id="✅-filter">✅ filter</h2>
<br />

<h3 id="🔎-filter로-아이템-삭제하기">🔎 filter로 아이템 삭제하기</h3>
<blockquote>
<p><code>filter()</code> 메소드를 활용해서 삭제 기능을 만들어보자.</p>
</blockquote>
<br />

<h4 id="📚-기능-1">📚 기능</h4>
<p>☑️ 보여줄 배열을 해당 요소가 제외된 배열로 변경
☑️ 배열이 바뀔 때마다 재렌더링을 해서 변경된 데이터를 보여주기</p>
<br />

<h4 id="📚-app-컴포넌트-변경">📚 App 컴포넌트 변경</h4>
<p>App 컴포넌트에서 기존에 사용하던 json 데이터를 <code>mockItems</code>라고 바꾸고, <code>items</code>라는 state의 초깃값으로 넣는다.</p>
<h4 id="📄-appjs-1">📄 App.js</h4>
<pre><code class="language-js">...
// import items from '../mock.json';
// 변경
import mockItems from '../mock.json';


function App() {
  const [order, setOrder] = useState('createdAt');
  // 추가
  const [items, setItems] = useState(mockItems);
    ...
}

export default App;</code></pre>
<br />

<h4 id="📚-메소드-활용-1">📚 메소드 활용</h4>
<p>삭제 기능 만들기!</p>
<p>🌠** 배열에서 특정 항목을 삭제할 때는 <code>filter()</code>라는 배열 메소드를 사용하면 된다.**</p>
<h4 id="📄-appjs-2">📄 App.js</h4>
<p>배열 각 요소를 구분하는 고유한 값인 id 를 활용해서 필터링</p>
<p>App 컴포넌트에다가 id 를 파라미터로 받는 handleDelete 함수를 만들고, 여기서 items state를 필터링된 배열로 변경해주기</p>
<pre><code class="language-js">const handleDelete = (id) =&gt; {
  const nextItems = items.filter((item) =&gt; item.id !== id);
  setItems(nextItems);
};</code></pre>
<br />

<h4 id="📚-삭제-함수-실행">📚 삭제 함수 실행</h4>
<p>삭제 버튼을 눌렀을 때 handleDelete &lt;- 이 함수가 실행되도록 만들자.</p>
<h4 id="📄-movielistjs">📄 MovieList.js</h4>
<pre><code class="language-js">&lt;MovieList items={sortedItems} onDelete={handleDelete} /&gt;</code></pre>
<p>MovieListItem 컴포넌트에서는 handleDeleteClick 이라는 함수를 만들고, 
onDelete Prop을 item.id 값으로 실행.</p>
<p>그리고 이 MovieListItem 함수를 삭제 버튼에 onClick 핸들러로 등록해준다.</p>
<pre><code class="language-js">function MovieListItem({ item, onDelete }) {
  // ...
  const handleDeleteClick = () =&gt; onDelete(item.id);

  return (
    &lt;div className=&quot;MovieListItem&quot;&gt;
      {/* ... */}
      &lt;button onClick={handleDeleteClick}&gt;삭제&lt;/button&gt;
    &lt;/div&gt;
  );
}

function MovieList({ items, onDelete }) {
  return (
    &lt;ul className=&quot;MovieList&quot;&gt;
      {items.map((item) =&gt; (
        &lt;li&gt;
          &lt;MovieListItem item={item} onDelete={onDelete} /&gt;
        &lt;/li&gt;
      ))}
    &lt;/ul&gt;
  );
}</code></pre>
<br />

<h4 id="📚-결과-1">📚 결과</h4>
<h4 id="📄-appjs-3">📄 App.js</h4>
<pre><code class="language-js">import { useState } from 'react';
import MovieList from './MovieList';
import mockItems from '../mock.json';

function App() {
  const [order, setOrder] = useState('createdAt');
  const [items, setItems] = useState(mockItems);

  const handleNewestClick = () =&gt; setOrder('createdAt');

  const handleBestClick = () =&gt; setOrder('rating');

  const handleDelete = (id) =&gt; {
    const nextItems = items.filter((item) =&gt; item.id !== id);
    setItems(nextItems);
  };

  const sortedItems = items.sort((a, b) =&gt; b[order] - a[order]);

  return (
    &lt;div&gt;
      &lt;button onClick={handleNewestClick}&gt;최신순&lt;/button&gt;
      &lt;button onClick={handleBestClick}&gt;베스트순&lt;/button&gt;
      &lt;MovieList items={sortedItems} onDelete={handleDelete} /&gt;
    &lt;/div&gt;
  );
}

export default App;
</code></pre>
<h4 id="📄-movielistjs-1">📄 MovieList.js</h4>
<pre><code class="language-js">import './MovieList.css';

function formatDate(value) {
  const date = new Date(value);
  return `${date.getFullYear()}. ${date.getMonth() + 1}. ${date.getDate()}`;
}

function MovieListItem({ item, onDelete }) {
  const { imgUrl, title, rating, content, createdAt } = item;

  const handleDeleteClick = () =&gt; onDelete(item.id);

  return (
    &lt;div className=&quot;MovieListItem&quot;&gt;
      &lt;img src={imgUrl} alt={title} /&gt;
      &lt;div&gt;{title}&lt;/div&gt;
      &lt;div&gt;{rating}&lt;/div&gt;
      &lt;div&gt;{content}&lt;/div&gt;
      &lt;div&gt;{formatDate(createdAt)}&lt;/div&gt;
      &lt;button onClick={handleDeleteClick}&gt;삭제&lt;/button&gt;
    &lt;/div&gt;
  );
}

function MovieList({ items, onDelete }) {
  return (
    &lt;ul className=&quot;MovieList&quot;&gt;
      {items.map((item) =&gt; (
        &lt;li&gt;
          &lt;MovieListItem item={item} onDelete={onDelete} /&gt;
        &lt;/li&gt;
      ))}
    &lt;/ul&gt;
  );
}

export default MovieList;
</code></pre>