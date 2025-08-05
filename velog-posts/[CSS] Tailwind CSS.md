<h2 id="✅-tailwind-css란">✅ Tailwind CSS란?</h2>
<blockquote>
<p>Tailwind CSS는 Utility-First 컨셉을 가진 CSS 프레임워크로, 
<strong>HTML 코드 내에서 직접 스타일을 적용할 수 있도록 미리 정의된 유틸리티 클래스를 제공한다.</strong></p>
</blockquote>
<p>부트스트랩과 비슷하게 m-1, flex와 같이 미리 세팅된 유틸리티 클래스를 활용하는 방식으로 HTML 코드 내에서 스타일링을 할 수 있다.</p>
<br />

<h3 id="🌠-atomic-css-utility-first란">🌠 Atomic CSS, Utility-first란?</h3>
<blockquote>
<p><strong>미리 정의된 작은 단위의 CSS 클래스(유틸리티 클래스)를 조합하여 웹 페이지의 스타일을 구성하는 방법론</strong></p>
</blockquote>
<p>각 CSS 속성을 CSS 클래스로 만들어, CSS 속성을 작성하는 게 아니라 미리 잘 정의된 클래스들을 가지고 조합해서 디자인을 적용하는 것.</p>
<p>인라인 스타일을 사용하는 것만큼 쉽고 빠르게 스타일링을 할 수 있으면서도 디자인 시스템만큼이나 일관된 디자인을 가능하게 해준다.</p>
<br />

<hr />
<br />

<h2 id="✅-사용하기">✅ 사용하기</h2>
<h3 id="🖥️-설치하기">🖥️ 설치하기</h3>
<p><a href="https://tailwindcss.com/docs/installation/using-vite#integration-guides">Tailwind CSS</a></p>
<h4 id="npm으로-tailwind-css-설치하기">npm으로 Tailwind CSS 설치하기</h4>
<pre><code class="language-bash">npm install tailwindcss@latest postcss@latest autoprefixer@latest</code></pre>
<br />

<h4 id="postcss-플러그인에-tailwind-css-추가하기">PostCSS 플러그인에 Tailwind CSS 추가하기</h4>
<pre><code class="language-js">// postcss.config.js 등의 postcss 설정 파일
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
};</code></pre>
<br />

<h4 id="설정-파일-생성하기">설정 파일 생성하기</h4>
<p>명령어를 입력하면 프로젝트 루트에 아래의 설정 파일이 생성된다. 기본 스타일이나 플러그인 등을 설정할 수 있는 파일이다.</p>
<pre><code class="language-bash">npx tailwindcss init</code></pre>
<pre><code class="language-js">// tailwind.config.js
module.exports = {
  purge: [],
  darkMode: false, // or 'media' or 'class'
  theme: {
    extend: {},
  },
  variants: {},
  plugins: [],
};</code></pre>
<br />

<h3 id="🎨-tailwind-css-스타일-추가하기">🎨 Tailwind CSS 스타일 추가하기</h3>
<p>메인 CSS 파일에 아래 코드를 추가하여 Tailwind CSS 스타일을 추가한다. <code>@tailwind</code> 디렉티브는 빌드 시에 CSS 코드로 변환된다.</p>
<pre><code class="language-css">@tailwind base;
@tailwind components;
@tailwind utilities;</code></pre>
<p>React나 Vue와 같이 CSS 파일을 JavaScript에 직접 임포트할 수 있는 경우에는 아래와 같이 JavaScript 코드에서 직접 임포트할 수도 있다.</p>
<pre><code class="language-js">// app.js
import &quot;tailwindcss/tailwind.css&quot;;</code></pre>
<br />

<hr />
<br />

<h2 id="✅-장점">✅ 장점</h2>
<h3 id="utility-first의-편리함과-빠른-개발">Utility-First의 편리함과 빠른 개발</h3>
<p>Utility-First 컨셉은 Tailwind CSS의 메인 컨셉이자 가장 큰 장점이다. Utility-First 덕에 매우 쉽고 빠르게 원하는 디자인을 개발할 수 있게 된다.</p>
<p>스타일 코드도 HTML 코드 안에 있기 때문에 HTML와 CSS 파일을 별도로 관리할 필요가 없다. 그 덕분에 HTML-CSS를 왔다갔다하며 시간을 쓰거나 위의 이미지처럼 화면을 분할해서 사용하지 않아도 된다. 또 원하는 태그의 스타일을 변경하기 위해 클래스명을 검색해가며 일일이 필요한 CSS 코드를 찾을 수고도 사라진다.
<br /></p>
<h3 id="일관된-디자인">일관된 디자인</h3>
<p>모든 곳에서 동일한 색상이나 사이즈, 간격 등의 유틸리티 클래스를 사용하므로 일관된 스타일로 구현하기가 수월하다.
<br /></p>
<h3 id="쉽고-자유로운-커스텀">쉽고 자유로운 커스텀</h3>
<p>다른 프레임워크들에 비해 기본 스타일 값을 디테일한 부분까지 쉽게 커스텀이 가능하다. 커스텀을 할 때 기본 스타일 값을 수정하는 방식이기에 디자인 일관성도 해치지 않는다. 덕분에 디자인 시스템이나 다크 모드 구현도 간편하다.
<br /></p>
<h3 id="로우-레벨의-스타일-제공">로우 레벨의 스타일 제공</h3>
<p>각 CSS 요소 수준의 유틸리티 클래스를 제공하기 때문에 세밀하게 원하는 디자인을 구현할 수 있다.
<br /></p>
<h3 id="intelli-sense">Intelli Sense</h3>
<p>_로우 레벨의 스타일을 제공한다는 것은 거의 모든 스타일의 유틸리티 클래스를 학습해야 한다는 의미와 같다. _</p>
<p> 이러한 불편을 해소하기 위해 Intelli Sense 플러그인을 제공한다. 미리보기, 자동완성, 신택스 하이라이팅, 린팅을 지원하기 때문에 조금만 익숙해지면 금방 문서 없이 개발할 수 있다.
<br /></p>
<h3 id="javascript-코드와의-분리">JavaScript 코드와의 분리</h3>
<p>Tailwind CSS는 JavaScript 코드와 완전히 분리되어 있다. 그러므로 프로젝트 진행 도중 JavaScript 프레임워크를 변경하여도 큰 추가 작업 없이 기존의 HTML 코드를 그대로 쓸 수 있다.</p>
<br />

<hr />
<br />

<h2 id="✅-단점">✅ 단점</h2>
<h3 id="html이-복잡하고-길어질-수-있다">HTML이 복잡하고 길어질 수 있다</h3>
<p>대부분의 스타일을 HTML 클래스에 직접 작성하는 방식이기 때문에, 복잡한 컴포넌트를 만들 경우 클래스가 지나치게 길어질 수 있다.</p>
<pre><code class="language-html">&lt;button class=&quot;bg-blue-500 hover:bg-blue-600 text-white font-semibold py-2 px-4 rounded shadow&quot;&gt;
  클릭
&lt;/button&gt;</code></pre>
<p>이렇게 한 요소에 많은 유틸리티 클래스가 붙다 보면, HTML 가독성이 떨어지고 유지보수가 어려워질 수 있다.</p>
<h3 id="초반-클래스명-러닝-커브">초반 클래스명 러닝 커브</h3>
<p>Tailwind CSS는 자체적인 클래스 네이밍 규칙을 사용한다. Tailwind만의 문법과 원리를 익히는 데 시간이 필요하다.</p>
<h3 id="javascript로-직접-스타일-조작이-어렵다">JavaScript로 직접 스타일 조작이 어렵다</h3>
<p>CSS-in-JS처럼 JavaScript 코드 안에서 직접 스타일 속성을 정의하거나 조작할 수 없다. Tailwind는 JavaScript 기반 스타일 제어에 한계가 있으며, 매우 세부적인 동적 스타일링이 필요한 상황에서는 불편하게 느껴질 수 있다.</p>
<h3 id="html와-css-코드-혼재">HTML와 CSS 코드 혼재</h3>
<p>Tailwind는 스타일을 CSS가 아닌 HTML 클래스에서 직접 조정하기 때문에 디자인 로직과 마크업이 뒤섞이면서 코드가 덜 직관적으로 느껴질 수 있다.
<br /></p>
<hr />
<h2 id="참고자료">참고자료</h2>
<p><a href="https://tailwindcss.com/">https://tailwindcss.com/</a>
<a href="https://wonny.space/writing/dev/hello-tailwind-css">https://wonny.space/writing/dev/hello-tailwind-css</a></p>