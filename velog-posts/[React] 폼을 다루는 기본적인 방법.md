<h2 id="✅-폼을-다루는-기본적인-방법">✅ 폼을 다루는 기본적인 방법</h2>
<p>스테이트를 만들고 <code>target.value</code> 값을 사용해서 값을 변경해 줄 수 있다.</p>
<pre><code class="language-jsx">function TripSearchForm() {
  // 1. value Prop으로 스테이트 값을 내려주고
  // 여행지, 체크인, 체크아웃 정보를 state로 관리한다.
  // 이 값들은 인풋의 value에 전달되어 &lt;제어 컴포넌트&gt;로 동작하게 된다.
  const [location, setLocation] = useState('Seoul');
  const [checkIn, setCheckIn] = useState('2022-01-01');
  const [checkOut, setCheckOut] = useState('2022-01-02');

  // 2. onChange Prop으로 핸들러 함수를 넘기기
  // onChange 이벤트에 연결되어 인풋 값을 실시간으로 반영한다.
  const handleLocationChange = (e) =&gt; setLocation(e.target.value);

  const handleCheckInChange = (e) =&gt; setCheckIn(e.target.value);

  const handleCheckOutChange = (e) =&gt; setCheckOut(e.target.value);

  return (
    &lt;form&gt;
      &lt;h1&gt;검색 시작하기&lt;/h1&gt;
    // 3. 제어 컴포넌트
    // value={location} // 인풋의 표시 값을 state에서 받아옴
    // onChange={handleLocationChange} // 입력이 바뀔 때 state 업데이트
      &lt;label htmlFor=&quot;location&quot;&gt;위치&lt;/label&gt;
      &lt;input id=&quot;location&quot; name=&quot;location&quot; value={location} placeholder=&quot;어디로 여행가세요?&quot; onChange={handleLocationChange} /&gt;
      &lt;label htmlFor=&quot;checkIn&quot;&gt;체크인&lt;/label&gt;
      &lt;input id=&quot;checkIn&quot; type=&quot;date&quot; name=&quot;checkIn&quot; value={checkIn} onChange={handleCheckInChange} /&gt;
      &lt;label htmlFor=&quot;checkOut&quot;&gt;체크아웃&lt;/label&gt;
      &lt;input id=&quot;checkOut&quot; type=&quot;date&quot; name=&quot;checkOut&quot; value={checkOut} onChange={handleCheckOutChange} /&gt;
      &lt;button type=&quot;submit&quot;&gt;검색&lt;/button&gt;
    &lt;/form&gt;
  )
}</code></pre>
<br />

<hr />
<br />

<h2 id="✅-폼-값을-객체-하나로-처리하기">✅ 폼 값을 객체 하나로 처리하기</h2>
<p>이벤트 객체의 <code>target.name</code> 과 <code>target.value</code> 값을 사용해서 값을 변경해 줄 수도 있다.</p>
<p><strong>🌠 이렇게하면 객체형 스테이트 하나만 가지고도 값을 처리할 수 있음.</strong></p>
<pre><code class="language-jsx">function TripSearchForm() {
  // 1. location, checkIn, checkOut 값을 하나의 객체로 관리
  const [values, setValues] = useState({
    location: 'Seoul',
    checkIn: '2022-01-01',
    checkOut: '2022-01-02',
  })
  // 2. 모든 input 요소에서 공통으로 사용할 수 있는 change 핸들러
  const handleChange = (e) =&gt; {
     // 이벤트 객체에서 name과 value를 꺼내서 해당 항목만 업데이트
    const { name, value } = e.target;
    // 기존 값은 유지하고, 변경된 name 속성의 값을 업데이트
    setValues((prevValues) =&gt; ({
      ...prevValues,
      [name]: value,
    }));
  }

  return (
    &lt;form&gt;
      &lt;h1&gt;검색 시작하기&lt;/h1&gt;
      &lt;label htmlFor=&quot;location&quot;&gt;위치&lt;/label&gt;
      // 3. name=&quot;location&quot; // name 속성이 객체 키와 연결
      &lt;input id=&quot;location&quot; name=&quot;location&quot; value={values.location} placeholder=&quot;어디로 여행가세요?&quot; onChange={handleChange} /&gt;
      &lt;label htmlFor=&quot;checkIn&quot;&gt;체크인&lt;/label&gt;
      &lt;input id=&quot;checkIn&quot; type=&quot;date&quot; name=&quot;checkIn&quot; value={values.checkIn} onChange={handleChange} /&gt;
      &lt;label htmlFor=&quot;checkOut&quot;&gt;체크아웃&lt;/label&gt;
      &lt;input id=&quot;checkOut&quot; type=&quot;date&quot; name=&quot;checkOut&quot; value={values.checkOut} onChange={handleChange} /&gt;
      &lt;button type=&quot;submit&quot;&gt;검색&lt;/button&gt;
    &lt;/form&gt;
  )
}</code></pre>
<br />

<hr />
<br />

<h2 id="✅-기본-submit-동작-막기">✅ 기본 submit 동작 막기</h2>
<pre><code class="language-jsx">const handleSubmit = (e) =&gt; {
  e.preventDefault();
  // ...
}</code></pre>
<br />

<hr />
<br />

<h2 id="✅-제어-컴포넌트와-비제어-컴포넌트">✅ 제어 컴포넌트와 비제어 컴포넌트</h2>
<h3 id="📄-제어-컴포넌트controlled-component">📄 제어 컴포넌트(Controlled Component)</h3>
<blockquote>
<p>인풋의 <code>value</code>를 리액트의 <code>useState</code> 같은 상태로 관리하는 컴포넌트를 말한다.</p>
</blockquote>
<p><strong>리액트로 <code>value</code>를 지정한다는 것이 핵심!</strong></p>
<p>입력값을 상태로 직접 관리하기 때문에 값이 어떻게 바뀌는지 추적하고, 조건에 따라 다르게 처리할 수 있다는 특징이 있다.
(<code>useState</code> 등으로 상태를 저장하고, <code>onChange</code> 이벤트를 통해 입력값이 바뀔 때마다 상태를 업데이트함으로써 인풋의 값을 제어한다.)</p>
<br />

<h3 id="📄-비제어-컴포넌트uncontrolled-component">📄 비제어 컴포넌트(Uncontrolled Component)</h3>
<blockquote>
<p>제어 컴포넌트와는 다르게 인풋의 value를 리액트 상태로 관리하지 않고, DOM 자체가 값을 관리하는 컴포넌트를 말한다.</p>
</blockquote>
<p>리액트의 상태 업데이트 없이도 값을 읽을 수 있고, 파일 업로드처럼 입력값을 자주 제어하지 않아도 되는 경우에 적합하다.</p>
<br />

<hr />
<br />

<h2 id="✅-html과-다른-점">✅ HTML과 다른 점</h2>
<h3 id="📄-onchange">📄 onChange</h3>
<blockquote>
<p>리액트에선 순수 HTML과 다르게 <code>onChange</code> Prop을 사용하면 입력 값이 바뀔 때마다 핸들러 함수를 실행한다.</p>
</blockquote>
<p> <code>oninput</code> 이벤트와 같다고 생각하면 된다.</p>
<h3 id="📄-htmlfor">📄 htmlFor</h3>
<blockquote>
<p><code>< label/></code> 태그에서 사용하는 속성인 for 는 자바스크립트 반복문 키워드인 for 와 겹치기 때문에 리액트에서는 <code>htmlFor</code> 를 사용</p>
</blockquote>