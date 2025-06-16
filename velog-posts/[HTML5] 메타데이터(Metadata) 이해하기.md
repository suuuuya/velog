<p><strong>SEO 최적화</strong>와 <strong>접근성</strong>을 위한 방법 중 하나인 <strong>메타데이터(Metadata)</strong> 이해하기
<br /><br /></p>
<h2 id="✅-메타데이터metadata란">✅ 메타데이터(Metadata)란?</h2>
<blockquote>
<p>HTML 메타테이터는 <strong>웹 페이지에 관한 정보를 제공하는 데이터</strong>로
 HTML 문서에 대한 데이터라고 할 수 있다.</p>
</blockquote>
<p>쉽게 말해 데이터를 설명하는 데이터다.</p>
<p>웹 페이지의 콘텐츠 자체와는 다르게 내용이 페이지에 직접 표시되지 않지만, 주로 브라우저나 검색 엔진에 페이지에 대한 추가적인 정보를 제공하기 위한 것이다. 
<br /><br /></p>
<h2 id="✅-메타데이터의-역할">✅ 메타데이터의 역할</h2>
<p>메타데이터는 검색 엔진 최적화(SEO), 소셜 미디어 공유, 접근성 등에 대한 영향을 준다.
<br /></p>
<h3 id="검색-엔진-최적화seo">검색 엔진 최적화(SEO)</h3>
<p>검색 엔진이 웹 페이지를 더 잘 이해하고 인덱싱할 수 있도록 정보를 제공한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/4a36125a-3bd2-4560-a7bb-9b9fcf047294/image.png" /></p>
<br />

<h3 id="sns-공유">SNS 공유</h3>
<p>OG(Open Graph) 태그는 SNS에 공유될 때, 웹 페이지의 미리보기를 제어한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/82970923-a19d-419f-8909-63fcb9ed753f/image.png" /> 링크를 SNS에 공유했을 때, 위와 같이 링크의 미리보기 화면에 이미지와 설명이 나타나 클릭하기 전에 무슨 콘텐츠인지 예측할 수 있는데, 이 미리보기 화면에서 중요한 역할을 하는 것이 메타데이터다.
<br /></p>
<h3 id="웹-접근성">웹 접근성</h3>
<p>메타데이터는 웹 사이트가 다양한 디바이스와 브라우저에서 올바르게 표시되도록 도와준다.
<br /><br /></p>
<h2 id="✅-메타데이터-요소">✅ 메타데이터 요소</h2>
<h3 id="title">title</h3>
<p>브라우저의 제목 표시줄이나 페이지 탭에 보여지는 문서의 제목을 지정한다.</p>
<pre><code class="language-html">&lt;title&gt;메타데이터(Metadata)란?&lt;/title&gt;</code></pre>
<br />

<h3 id="base">base</h3>
<p>HTML 문서에 포함된 모든 상대 URL들의 기준 URL를 지정한다.
한 문서에 하나의 <code>&lt;base /&gt;</code> 요소만 포함 가능하다.</p>
<ul>
<li>href: 기준 URL</li>
<li>target: target 속성을 사용하는 요소(<code>&lt;a&gt;</code>)의 기본값</li>
</ul>
<pre><code class="language-html">&lt;base href=&quot;http://www.example.com/page.html&quot; /&gt;
&lt;base target=&quot;_blank&quot; /&gt;
&lt;base target=&quot;_target&quot; href=&quot;http://www.example.com/page.html&quot; /&gt;</code></pre>
<br />

<h3 id="link">link</h3>
<p>외부 리소스(HTML, CSS, Icon 등)의 연결 및 현재 문서와의 관계를 명시한다.</p>
<ul>
<li>rel: (필수)현재 문서와 외부 리소스와의 관계</li>
<li>href: 외부 리소스의 URL</li>
<li>type: 외부 리소스의 MIME 타입</li>
</ul>
<pre><code class="language-html">&lt;link href=&quot;style.css&quot; rel=&quot;stylesheet&quot; /&gt;
&lt;link rel=&quot;icon&quot; href=&quot;favicon.ico&quot; /&gt;
&lt;link rel=&quot;apple-touch-icon&quot; sizes=&quot;114x114&quot; href=&quot;apple-icon-114.png&quot; type=&quot;image/png&quot; /&gt;
&lt;link href=&quot;print.css&quot; rel=&quot;stylesheet&quot; media=&quot;print&quot; /&gt;</code></pre>
<br />

<h3 id="stylescript">style/script</h3>
<p>문서나 문서 일부에 대한 정보(CSS/JS)를 지정한다.</p>
<pre><code class="language-html">&lt;style&gt; ... &lt;/style&gt;
&lt;script&gt; ... &lt;/script&gt;</code></pre>
<br />

<h3 id="meta">meta</h3>
<p>검색엔진이나 브라우저에 정보 제공
(자세한 내용은 아래에 이어서,, 😀)
<br /><br /></p>
<h2 id="✅-메타태그metatag">✅ 메타태그(MetaTag)</h2>
<p><code>&lt;meta&gt;</code>태그는 문서의 정보를 작성하는 태그로, 여러 개의 정보를 저장할 수 있다. <code>&lt;meta&gt;</code>태그는 name 속성을 메타데이터의 이름, content 속성을 값으로 하여 메타데이터를 추가한다.
<br /></p>
<h3 id="charset-문자-인코딩">Charset (문자 인코딩)</h3>
<pre><code class="language-HTML">&lt;meta charset=&quot;utf-8&quot; /&gt;</code></pre>
<p>위 코드에서 <code>&lt;meta charset="utf-8"&gt;</code>는 meta 태그의 charset(문자셋) 속성으로 인코딩 방식을 지정하는 것이다. 다양한 브라우저상에서 인코딩 방식의 통일을 주기 위해 작성한다. 작성하지 않으면 문서 파일의 글씨가 깨질 수 있다.
<br /></p>
<h3 id="author">author</h3>
<p>문서 제작자 정보를 나타내는 author.
문서를 작성한 사람에 대한 정보를 추가하는 메타데이터 이름이다.</p>
<pre><code class="language-html">&lt;meta name=&quot;author&quot; content=&quot;SUYA&quot;&gt;</code></pre>
<br />

<h3 id="description">description</h3>
<p>페이지에 대한 짧고 정확한 요약을 추가하는 메타데이터. 여러 브라우저에서는 즐겨찾기 페이지의 기본 설명 값으로 description의 값을 사용하기도 한다.</p>
<pre><code class="language-html">&lt;meta name=&quot;description&quot; content=&quot;메타데이터 이해하기&quot;&gt;</code></pre>
<br />

<h3 id="keywords">keywords</h3>
<p>웹 페이지의 콘텐츠와 관련된 키워드를, 구분을 위한 쉼표를 이용해 원하는 개수만큼 추가할 수 있다.</p>
<pre><code class="language-html">&lt;meta name=&quot;keywords&quot; content=&quot;meta, metadata, mata tag, 메타테이터, SEO&quot;&gt;</code></pre>
<br />

<h3 id="robots-크롤러-지시">Robots (크롤러 지시)</h3>
<p>검색 로봇, 크롤러에 대한 content 속성을 설정한다.</p>
<pre><code class="language-html">&lt;meta name=&quot;robots&quot; content=&quot;index, follow&quot;&gt;</code></pre>
<h4 id="content-속성-종류">content 속성 종류</h4>
<ul>
<li>noindex : 검색 결과에 이 페이지를 표시 하지 않는다.</li>
<li>nofollow : 이 페이지의 링크를 따라가지 않는다.</li>
<li>noarchive : 검색결과에 저장된 페이지 링크를 표시하지 않는다.</li>
<li>All(기본값) : 색인 생성이나 게재에 대한 제한이 없다, 기본값이므로 명시적으로 표시해도 효과 없음</li>
<li>Non : noindex, nofollow와 같다</li>
<li>index : 그 페이지를 수집대상으로 한다.</li>
<li>Follow : 그 페이지를 포함해 링크가 걸린 곳을 수집대상으로 한다.</li>
</ul>
<p>예를 들어, 현재 개발중일 경우에는 noindex, nofollow를 설정하여 페이지가 구글에 노출되지 않게 설정할 수 있다.
<br /></p>
<h3 id="viewport">viewport</h3>
<p>모바일 기기에서의 사용을 위한 뷰포트. 
메타 뷰포트는 PC 화면에서 보이는 페이지를 모바일 기기에서 보기 위해 추가하는 정보다. </p>
<p>🌠 <strong>뷰포트란? 웹 페이지가 브라우저 창에서 보이는 영역</strong></p>
<pre><code class="language-html">&lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot;&gt;
&lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1, minimum-scale=1, maximum-scale, user-scalable=no&quot;&gt;</code></pre>
<ul>
<li>name=&quot;viewport&quot; 설정으로 반응형 웹 사이트를 제작할 수 있다.</li>
<li>width=device-width: 장치의 화면 너비를 따르도록 페이지 너비를 설정</li>
<li>initial-scale=1: 브라우저에서 페이지를 처음 로드할 때 배율을 1로 설정</li>
<li>minimum-scale=1: 최소사이즈를 1배로 처리해서 축소를 못하게 막기</li>
<li>maximum-scale=1: 최대사이즈를 1배로 처리해서 확대를 못하게 막기</li>
<li>user-scalable=no: 사용자크기변화를 no로 처리해서 크기변화를 못하게 막기<br />

</li>
</ul>
<h3 id="open-graph-소셜-미디어">Open Graph (소셜 미디어)</h3>
<p>웹 페이지가 인스타그램, 페이스북과 같이 소셜 미디어에서 공유될 때 페이지의 내용을 정의하는 역할을 한다.</p>
<pre><code class="language-html">&lt;meta property=&quot;og:title&quot; content=&quot;웹페이지 제목&quot;&gt;
&lt;meta property=&quot;og:description&quot; content=&quot;웹페이지 설명&quot;&gt;
&lt;meta property=&quot;og:image&quot; content=&quot;이미지 URL&quot;&gt;
&lt;meta property=&quot;og:url&quot; content=&quot;웹페이지 URL&quot;&gt;
&lt;meta property=&quot;og:type&quot; content=&quot;웹페이지 유형&quot;&gt;
&lt;meta property=&quot;og:site_name&quot; content=&quot;Site Name&quot;&gt;
&lt;meta property=&quot;og:locale&quot; content=&quot;ko&quot;&gt;
</code></pre>
<h4 id="카카오톡-공유-디버거">카카오톡 공유 디버거</h4>
<p><a href="https://accounts.kakao.com/login/simple/?continue=https%3A%2F%2Fdevelopers.kakao.com%2Flogin%3Fcontinue%3D%252Ftool%252Fdebugger%252Fsharing&amp;talk_login=#simpleLogin">https://accounts.kakao.com/login/simple/?continue=https%3A%2F%2Fdevelopers.kakao.com%2Flogin%3Fcontinue%3D%252Ftool%252Fdebugger%252Fsharing&amp;talk_login=#simpleLogin</a></p>
<h4 id="x-공유-디버거">X 공유 디버거</h4>
<p><a href="https://x.com/i/flow/login?input_flow_data=%7B%22requested_variant%22%3A%22eyJyZWRpcmVjdF9hZnRlcl9sb2dpbiI6Imh0dHBzOi8vY2FyZHMtZGV2LnR3aXR0ZXIuY29tL3ZhbGlkYXRvciJ9%22%7D">https://x.com/i/flow/login?input_flow_data=%7B%22requested_variant%22%3A%22eyJyZWRpcmVjdF9hZnRlcl9sb2dpbiI6Imh0dHBzOi8vY2FyZHMtZGV2LnR3aXR0ZXIuY29tL3ZhbGlkYXRvciJ9%22%7D</a></p>
<h4 id="페이스북-공유-디버거">페이스북 공유 디버거</h4>
<p><a href="https://developers.facebook.com/tools/debug/">https://developers.facebook.com/tools/debug/</a>
<br /></p>
<h3 id="theme-color-브라우저-테마-색상">Theme-Color (브라우저 테마 색상)</h3>
<p>모바일 브라우저의 툴바 색상을 설정하는 역할을 한다.</p>
<pre><code class="language-html">&lt;meta name=&quot;theme-color&quot; content=&quot;#111111&quot;&gt;</code></pre>
<br />

<h3 id="application-name">Application Name</h3>
<p>웹 페이지에서 구동 중인 애플리케이션의 이름을 나타낸다.</p>
<pre><code class="language-html">&lt;meta name=&quot;application-name&quot; content=&quot;Pikmin Bloom&quot;&gt;</code></pre>
<br />

<h3 id="mobile-application">Mobile Application</h3>
<p>모바일 앱이 존재하는 경우 앱으로 연결 시 노출</p>
<pre><code class="language-html">&lt;--iOS--&gt;
&lt;meta property=&quot;al:ios:url&quot; content=&quot; ios 앱 URL&quot; /&gt;
&lt;meta property=&quot;al:ios:app_store_id&quot; content=&quot;ios 앱스토어 ID&quot; /&gt; 
&lt;meta property=&quot;al:ios:app_name&quot; content=&quot;ios 앱 이름&quot; /&gt; 
&lt;--Android--&gt;
&lt;meta property=&quot;al:android:url&quot; content=&quot;안드로이드 앱 URL&quot; /&gt;
&lt;meta property=&quot;al:android:app_name&quot; content=&quot;안드로이드 앱 이름&quot; /&gt;
&lt;meta property=&quot;al:android:package&quot; content=&quot;안드로이드 패키지 이름&quot; /&gt; 
&lt;meta property=&quot;al:web:url&quot; content=&quot;안드로이드 앱 URL&quot; /&gt;</code></pre>
<br />

<hr />
<h2 id="참고자료">참고자료</h2>
<p><a href="https://developer.mozilla.org/ko/docs/Learn_web_development/Core/Structuring_content/Webpage_metadata">https://developer.mozilla.org/ko/docs/Learn_web_development/Core/Structuring_content/Webpage_metadata</a>
<a href="https://developer.mozilla.org/ko/docs/Web/HTML/Reference/Elements/meta">https://developer.mozilla.org/ko/docs/Web/HTML/Reference/Elements/meta</a></p>