<h2 id="✅-styled-components란">✅ Styled Components란?</h2>
<blockquote>
<p>styled-components는 React 애플리케이션에서 스타일을 작성하기 위한 CSS-in-JS 라이브러리다.</p>
</blockquote>
<h4 id="☑️-특징">☑️ <strong>특징</strong></h4>
<ul>
<li><strong>컴포넌트 기반 스타일링</strong>
: 재사용성과 유지보수성을 높여준다.</li>
<li><strong>CSS-in-JS</strong>
: JavaScript 파일 내에서 CSS를 작성하여 스타일과 로직을 함께 관리할 수 있다.</li>
<li><strong>동적 스타일링</strong>
: JavaScript의 기능을 활용하여 조건부 스타일 적용이 가능하다.</li>
<li><strong>자동 CSS 클래스 관리</strong>
: 중복되는 CSS 클래스 이름을 신경 쓰지 않고 자동으로 관리해준다.</li>
<li><strong>테마 지원</strong>
: 테마를 쉽게 적용하고 변경할 수 있도록 지원한다. </li>
</ul>
<p><br /><br /></p>
<h3 id="🖥️-설치">🖥️ 설치</h3>
<p>styled-components를 사용하기 위해서는 해당 라이브러리를 프로젝트에 설치해야 한다.</p>
<p>이전 버전 설치 이슈 때문에 최신 버전을 설치하는것이 안전.</p>
<pre><code class="language-bash">npm install styled-components@latest</code></pre>
<br />

<h3 id="📄-기본-사용법">📄 기본 사용법</h3>
<pre><code class="language-jsx">import styled from 'styled-components';

const Button = styled.button`
  padding: 8px 16px;
  font-size: 16px;
  background-color: #f0f0f0;
  color: #333;
  border: none;
  border-radius: 4px;
  cursor: pointer;

  &amp;:hover {
    background-color: #ddd;
  }
`;

// 컴포넌트 사용 예시
const App = () =&gt; {
  return &lt;Button&gt;Click Me&lt;/Button&gt;;
};</code></pre>
<br />

<h3 id="🌠-props-활용">🌠 Props 활용</h3>
<p>styled-components는 Props를 활용하여 동적으로 스타일을 설정할 수 있다.</p>
<pre><code class="language-jsx">import styled from 'styled-components';

const Button = styled.button`
  padding: 8px 16px;
  font-size: 16px;
  background-color: ${props =&gt; props.primary ? '#f00' : '#0f0'};
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
`;

// 컴포넌트 사용 예시
const App = () =&gt; {
  return (
    &lt;div&gt;
      &lt;Button&gt;Default&lt;/Button&gt;
      &lt;Button primary&gt;Primary&lt;/Button&gt;
    &lt;/div&gt;
  );
};</code></pre>
<br />

<h3 id="🌠-global-스타일">🌠 Global 스타일</h3>
<p>styled-components를 사용하면 전역 스타일을 설정할 수도 있다.
createGlobalStyle 함수를 사용하여 전역 스타일을 생성하고, 해당 컴포넌트를 최상위 컴포넌트에 추가한다.</p>
<pre><code>import styled, { createGlobalStyle } from 'styled-components';

const GlobalStyle = createGlobalStyle`
  body {
    font-family: Arial, sans-serif;
    background-color: #f5f5f5;
  }
`;

const App = () =&gt; {
  return (
    &lt;&gt;
      &lt;GlobalStyle /&gt;
      {/* 나머지 컴포넌트들 */}
    &lt;/&gt;
  );
};</code></pre><br />

<hr />
<br />

<h2 id="✅-styled-components를-사용하는-이유">✅ Styled Components를 사용하는 이유</h2>
<p>기존 CSS 방식에서 겪는 문제들을 <code>styled Components</code>를 통해 해결할 수 있다.
<br /></p>
<h3 id="css-클래스-이름-충돌">CSS 클래스 이름 충돌</h3>
<p>기존 CSS에서는 같은 클래스 이름이 여러 컴포넌트나 파일에서 중복되어 사용될 수 있다.
이로 인해 스타일이 의도치 않게 꼬이는 경우가 많아지며, 전역적으로 적용되는 클래스명이기 때문에 import하지 않은 CSS 파일에 같은 클래스명이 있을 경우 그 스타일도 함께 적용되는 문제가 발생한다.</p>
<blockquote>
<p><code>Styled Components</code>는 이러한 문제를 해결하기 위해 내부적으로 클래스 이름을 자동으로 고유하게 생성한다. 이를 통해 클래스 이름 충돌이 발생하지 않도록 설계되어, 스타일이 컴포넌트 단위로 안전하게 분리된다.</p>
</blockquote>
<br />

<h3 id="스타일-재사용과-관리의-어려움">스타일 재사용과 관리의 어려움</h3>
<p>기존 CSS에서는 공통 클래스를 만들어 쓰더라도, 어디서 어떤 클래스가 사용되는지 추적하기 어렵고, 스타일 변경 시 그 영향을 관리하기가 어려운 점이 있었다. 또한 동적인 스타일 적용이 어렵다는 문제도 존재했다.</p>
<blockquote>
<p><code>Styled Components</code>는 스타일을 JavaScript 변수나 함수처럼 다룰 수 있게 해준다. 이를 통해 스타일을 동적으로 조정하거나 props를 활용하여 쉽게 변경할 수 있다. 또한, 에디터에서 바로 확인하거나 수정이 가능해 유지보수와 재사용이 용이하다. 이 덕분에 코드의 재사용성과 관리가 크게 개선된다.</p>
</blockquote>