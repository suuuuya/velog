<p>데이터 가져오는 방법을 예제를 통해 이해해보기
<br /><br /></p>
<h2 id="✅-fetch">✅ fetch</h2>
<p>기본적인 데이터 요청</p>
<blockquote>
<p><strong><code>fetch()</code> 함수를 사용해서 데이터 가져오기</strong></p>
</blockquote>
<br />

<h4 id="📚-예제">📚 예제</h4>
<h4 id="📄-apijs">📄 api.js</h4>
<p><code>fetch()</code> 함수를 사용해서 리스폰스를 받고, 
리스폰스 객체의 <code>json()</code> 메소드를 사용해서 리스폰스 바디를 리턴한다.</p>
<pre><code class="language-js">export async function getFoods() {
  const response = await fetch('가져올 api url');
  const body = await response.json();
  return body;
}
</code></pre>
<h4 id="📄-appjs">📄 App.js</h4>
<pre><code class="language-js">import { useState } from 'react';
// ❗api
import { getFoods } from '../api';

// ❗getFoods() 함수를 handleLoadClick 함수에 실행
// ❗받아온 바디 중에서 foods 값만 Destructuring해서
// ❗items  state를 변경해준다.
const handleLoadClick = async () =&gt; {
  const { foods } = await getFoods();
  setItems(foods);
};
</code></pre>
<br />

<hr />
<br />

<h2 id="✅-useeffect">✅ useEffect</h2>
<p>여러 상태 관리가 필요한 경우</p>
<p><code>useEffect()</code>는 컴포넌트가 렌더링된 후 어떤 일을 실행하는 함수
<br /></p>
<p>❓** 언제 쓰는가?**</p>
<p>☑️ API 호출 (데이터 불러오기)
☑️ DOM 조작
☑️ 이벤트 리스너 등록
☑️ 타이머 설정
☑️ 컴포넌트가 언마운트될 때 정리 작업
<br /></p>
<h4 id="🔎-기본-문법">🔎 기본 문법</h4>
<p>배열이 <code>[]</code>면 처음 한 번만 실행한다.</p>
<pre><code class="language-js">useEffect(() =&gt; {
  // 실행할 코드
}, []);</code></pre>
<br />

<h4 id="🔎-값이-바뀔-때마다-실행하기">🔎 값이 바뀔 때마다 실행하기</h4>
<pre><code class="language-js">useEffect(() =&gt; {
  // 실행할 코드
}, [dep1, dep2, dep3, ...]);</code></pre>
<br />

<hr />
<br />

<h2 id="✅-pagenation">✅ pagenation</h2>
<blockquote>
<p>Pagination은 많은 데이터를 여러 페이지로 나눠서 보여주는 방식</p>
</blockquote>
<br />
Pagination은 크게 두 가지가 있다.

<p>☑️ <strong>오프셋 기반 페이지네이션</strong>
: <code>Offset</code> 방식은 페이지 번호나 받아온 데이터 갯수를 기준으로 데이터를 가져온다.
☑️ <strong>커서 기반 페이지네이션</strong>
:  <code>Cursor</code> 방식은 데이터를 가리키는 커서. 특정 데이터의 고유 id, key 값을 기준으로 가져온다는 차이가 있다.
<br /></p>
<p><code>Offset</code> 방식은 데이터가 추가/삭제되면 페이지가 밀려서 중복 또는 누락이 생길 수 있기 때문에, 데이터 변경이 적고 페이지 번호 이동이 중요한 경우에는 <code>Offset</code> 방식을 사용하는 것이 적합하다.</p>
<p><code>Cursor</code> 방식은 데이터의 중복/누락없이 가져올 수 있다는 장점이 있어서 대규모 데이터, 무한 스크롤, 실시간 피드가 중요한 경우에는 <code>Cursor</code> 방식을 사용하는게 적합한데, 대신 서버 입장에선 <code>Offset</code> 방식보다 만들기 까다롭다는 점이 있다.</p>