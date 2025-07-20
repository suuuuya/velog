<p>클래스네임을 좀 더 편리하게 쓰는 방법에 대해 알아보자.
<br /><br /></p>
<h2 id="✅-다양한-디자인-적용-방법">✅ 다양한 디자인 적용 방법</h2>
<br />

<h3 id="📄-이미지-불러오기">📄 이미지 불러오기</h3>
<blockquote>
<p>이미지 파일은 <code>import</code> 구문을 통해 불러오고,
불러온 이미지 주소를 <code>src</code>속성을 사용한다.</p>
</blockquote>
<pre><code class="language-js">import diceImg from './assets/dice.png';

function Dice() {
  return &lt;img src={diceImg} alt=&quot;주사위 이미지&quot; /&gt;;
}</code></pre>
<p><br /><br /></p>
<h3 id="📄-인라인-스타일">📄 인라인 스타일</h3>
<blockquote>
<p>객체에 카멜 표기법으로 작성한 프로퍼티 이름으로 스타일 속성을 작성한다.</p>
</blockquote>
<pre><code class="language-js">const style = {
  borderRadius: '50%',
  width: '120px',
  height: '120px',
};

function Dice() {
  return &lt;img style={style} .. /&gt;;
}
</code></pre>
<p><br /><br /></p>
<h3 id="📄-css-파일-불러오기">📄 CSS 파일 불러오기</h3>
<blockquote>
<p><code>import</code>구문에 <code>from</code>키워드 없이 쓴다.</p>
</blockquote>
<pre><code class="language-js">import './Dice.css';</code></pre>
<p><br /><br /></p>
<h3 id="📄-클래스네임-사용하기">📄 클래스네임 사용하기</h3>
<blockquote>
<p>CSS 파일에 정의된 클래스명을 <code>className</code> prop에 문자열로 넣어준다.</p>
</blockquote>
<p>☑️ <strong>재사용성을 위해 <code>className</code> prop을 부모 컴포넌트에서 받으면 더 좋다.</strong></p>
<pre><code class="language-js">import './Dice.css';

function Dice({ className = '' }) {
  const classNames = `Dice ${className}`;
  return &lt;img className={classNames} .. /&gt;;
}</code></pre>
<br />

<hr />
<br />


<h2 id="✅-편리하게-클래스네임을-쓰는-방법">✅ 편리하게 클래스네임을 쓰는 방법</h2>
<br />

<h3 id="📄-템플릿-문자열을-사용한-예">📄 템플릿 문자열을 사용한 예</h3>
<pre><code class="language-js">function Button({ isPending, color, size, invert, children }) {
  const classNames = `Button ${isPending ? 'pending' : ''} ${color} ${size} ${invert ? 'invert' : ''}`;
  return &lt;button className={classNames}&gt;{children}&lt;/button&gt;;
}

export default Button;
</code></pre>
<p><br /><br /></p>
<h3 id="📄-배열을-사용한-예">📄 배열을 사용한 예</h3>
<pre><code class="language-js">function Button({ isPending, color, size, invert, children }) {
  const classNames = [
    'Button',
    isPending ? 'pending' : '',
    color,
    size,
    invert ? 'invert' : '',
  ].join(' ');
  return &lt;button className={classNames}&gt;{children}&lt;/button&gt;;
}

export default Button;
</code></pre>
<p>☑️ <strong>위 예시의 단점은,</strong>
지저분하게 느껴지고, 매번 반복되는 코드를 작성한다는 번거로움이 있다. 
이럴 때 라이브러리를 사용한다.</p>
<br />

<hr />
<br />

<h2 id="✅-classnames-라이브러리">✅ classnames 라이브러리</h2>
<blockquote>
<p><code>classnames</code>은 NPM을 통해 설치할 수 있다.</p>
</blockquote>
<br />

<h3 id="🖥️-터미널-classnames-라이브러리-설치">🖥️ 터미널 classnames 라이브러리 설치</h3>
<pre><code class="language-bash">npm install classnames</code></pre>
<br />

<h3 id="📄-적용-예시">📄 적용 예시</h3>
<p>설치한 다음, <code>import</code> 로 불러와서 사용하면된다.</p>
<pre><code class="language-js">import classNames from 'classnames';

function Button({ isPending, color, size, invert, children }) {
  return (
    &lt;button
      className={classNames(
        'Button',
        isPending &amp;&amp; 'pending',
        color,
        size,
        invert &amp;&amp; 'invert',
      )}&gt;
     { children }
   &lt;/button &gt;
  );
}

export default Button;
</code></pre>
<p><a href="https://www.npmjs.com/package/classnames">🌠 NPM | classnames 패키지</a>
<br /></p>
<hr />
<h2 id="참고자료">참고자료</h2>
<p>코드잇 | 리액트 웹 개발 기초</p>