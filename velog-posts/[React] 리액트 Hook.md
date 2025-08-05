<h2 id="✅-hook이란">✅ Hook이란?</h2>
<blockquote>
<p>리액트에서 <code>state</code> 와 기타 리액트 기능을 함수형 컴포넌트에도 사용할 수 있게 해주는 특별한 함수다.</p>
</blockquote>
<p>리액트에서 Hooks 패턴을 사용하면 클래스형 컴포넌트를 작성하지 않고도 대부분의 기능을 구현 할 수 있다.
<br /></p>
<hr />
<br />

<h2 id="✅-usestate">✅ useState</h2>
<blockquote>
<p><code>useState</code>는 가장 기본적인 Hook 으로서, 함수형 컴포넌트에서도 가변적인 상태를 지니고 있을 수 있게 해준다. </p>
</blockquote>
<p>만약에 함수형 컴포넌트에서 상태를 관리해야 되는 일이 발생한다면 이 Hook 을 사용한다.</p>
<br />

<hr />
<br />

<h2 id="✅-useeffect">✅ useEffect</h2>
<blockquote>
<p><code>useEffect</code> 는 리액트 컴포넌트가 렌더링 될 때마다 특정 작업을 수행하도록 설정 할 수 있는 Hook이다.</p>
</blockquote>
<br />

<hr />
<br />

<h2 id="✅-usecontext">✅ useContext</h2>
<blockquote>
<p>이 Hook 을 사용하면 함수형 컴포넌트에서 Context 를 보다 더 쉽게 사용 할 수 있다.</p>
</blockquote>
<br />

<hr />
<br />

<h2 id="✅-usereducer">✅ useReducer</h2>
<blockquote>
<p><code>useReducer</code> 는 useState 보다 컴포넌트에서 더 다양한 상황에 따라 다양한 상태를 다른 값으로 업데이트해주고 싶을 때 사용하는 Hook이다.</p>
</blockquote>
<br />

<hr />
<br />

<h2 id="✅-usememo">✅ useMemo</h2>
<blockquote>
<p><code>useMemo</code> 를 사용하면 함수형 컴포넌트 내부에서 발생하는 연산을 최적화 할 수 있다.</p>
</blockquote>
<br />

<hr />
<br />

<h2 id="✅-usecallback">✅ useCallback</h2>
<blockquote>
<p><code>useCallback</code> 은 useMemo와 상당히 비슷한 함수로,
주로 렌더링 성능을 최적화해야 하는 상황에서 사용한다.</p>
</blockquote>
<p>이 Hook을 사용하면 이벤트 핸들러 함수를 필요할 때만 생성 할 수 있다.</p>
<br />

<hr />
<br />

<h2 id="✅-useref">✅ useRef</h2>
<blockquote>
<p><code>useRef</code> Hook 은 함수형 컴포넌트에서 ref 를 쉽게 사용 할 수 있게 해준다.</p>
</blockquote>
<br />

<hr />
<br />

<h2 id="✅-다른-hooks">✅ 다른 Hooks</h2>
<blockquote>
<p>다른 개발자들이 만든 <code>Hooks</code> 도 라이브러리로 설치하여 사용 할 수 있다.</p>
</blockquote>
<p><a href="https://nikgraf.github.io/react-hooks/">https://nikgraf.github.io/react-hooks/</a>
<a href="https://github.com/rehooks/awesome-react-hooks">https://github.com/rehooks/awesome-react-hooks</a></p>
<br />

<hr />
<br />

<h2 id="✅-리액트-hook을-사용할-때-지켜야-하는-규칙">✅ 리액트 hook을 사용할 때 지켜야 하는 규칙</h2>
<h4 id="반드시-리액트-컴포넌트-함수나-커스텀-hook-함수-안에서-실행되어야-함">반드시 리액트 컴포넌트 함수나 커스텀 Hook 함수 안에서 실행되어야 함</h4>
<ul>
<li>일반적인 자바스크립트 함수에서 호출 불가 ⇒ 오류 발생<br />

</li>
</ul>
<h4 id="반드시-함수의-최상위에서--호출되어야-함">반드시 함수의 최상위에서  호출되어야 함</h4>
<ul>
<li>반복문이나 조건문, 중첩된 함수 안에서는 사용 불가</li>
<li>리액트는 모든 렌더링에서 훅이 호출되는 순서가 항상 같음</li>
</ul>
<p>반복문이나 조건문에 의해 렌더링 간에 훅을 건너뛰게 되면 훅 호출 순서가 달라지기 때문에 버그 발생</p>
<br />

<hr />
<h2 id="참고자료">참고자료</h2>
<ul>
<li>팀미팅 스레드</li>
<li><a href="https://velog.io/@velopert/react-hooks">블로그 참고</a></li>
</ul>