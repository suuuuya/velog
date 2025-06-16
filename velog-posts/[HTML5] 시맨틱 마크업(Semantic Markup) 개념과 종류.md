<p>내가 구축한 웹사이트가 검색엔진 상위에 노출되고, 사용자에게도 명확한 정보를 제공하고 싶다면?
그 시작과 핵심은 <strong>시맨틱 마크업</strong>에 있다.
<br /><br /></p>
<h2 id="시맨틱semantic이란">시맨틱(Semantic)이란?</h2>
<blockquote>
<p>시맨틱 단어 자체에는 <strong>'의미의, 의미론적인'</strong> 라는 뜻이 담겨있다.
<strong>각각의 의미와 용도가 정해져 있다</strong>는 뜻으로도 볼 수 있다.</p>
</blockquote>
<p>태그 내용에 의미를 부여하는 태그가 <code><strong>시맨틱 태그(Semantic Tag)</strong></code>,
의미에 맞는 적절한 시맨틱 태그를 사용해 마크업 하는 것이 <code><strong>시맨틱 마크업(Semantic Markup)</strong></code>이다.
<br /><br /></p>
<h2 id="✅-시맨틱-마크업의-특징">✅ 시맨틱 마크업의 특징</h2>
<p>왜 시맨틱 마크업을 해야하냐?
<code><strong>가독성</strong></code>과 <code><strong>검색 엔진 최적화(SEO)</strong></code>, <code><strong>웹 접근성</strong></code> 측면에 이점이 있다.
<br /></p>
<h3 id="·-가독성">· 가독성</h3>
<p>애매모호한 <code>&lt;div&gt;</code> 구성보다는 적절한 <code>시맨틱 태그</code> 사용이 확실한 이해를 가진다. 
이해가 쉬운 구조는 유지보수가 쉽기도 하고, 문서 구조를 명확히 해서 가독성을 높인다.</p>
<p>🌠 <strong>너무 의미에만 집중하다보면 작성의 어려움을 느낄 수 있어 자신만의 규칙을 만들어 사용하는 것이 좋을 것 같다.</strong>
<br /></p>
<h3 id="·-검색-엔진-최적화-seo">· 검색 엔진 최적화 (SEO)</h3>
<p>내 웹 사이트가 검색 결과에 잘 노출 되고, 높은 트래픽을 유도하기 위해선 최적화 하는 과정이 중요한데, 시맨틱 태그 사용은 검색 엔진이 <u>페이지의 주요 콘텐츠를 식별하고 인덱싱<sup><a href="https://api.velog.io/rss/@iamsuuya#fn-def-1" id="fn-1">[1]</a></sup>하는 데 도움</u>을 준다.</p>
<div style="font-size: 0.8em;">
  <a href="https://api.velog.io/rss/@iamsuuya#fn-1" id="fn-def-1">[1]</a> 인덱싱(Indexing)이란, 검색 엔진이 페이지를 분석하고 해당 페이지 콘텐츠를 DB에 저장하는 과정을 말한다.
</div>

<p>🌠 <strong>SEO 주요 목적은..</strong> <code><strong>검색 결과 노출</strong></code>,&nbsp;<code><strong>검색 순위 향상</strong></code>,&nbsp;<code><strong>검색 엔진 이해</strong></code>,&nbsp;<code><strong>사용자 경험 개선</strong></code>
<br /></p>
<h3 id="·-웹-접근성">· 웹 접근성</h3>
<p>스크린 리더 등 보조기기를 사용하는 사용자에게 빠르게 탐색할 수 있도록 돕고, 페이지 구조와 내용을 명확히 전달하기 때문에 모든 사용자가 콘텐츠를 잘 이용할 수 있게 된다. 
<br /><br /></p>
<h2 id="✅-시맨틱-태그의-종류">✅ 시맨틱 태그의 종류</h2>
<p><code><strong>div</strong></code>와 같은 기능을 하지만 <strong>의미가 담겨 있는 태그</strong>들을 <code><strong>시맨틱 태그</strong></code>라고 하는데 사용법이 있다기보다 마크업을 작성하는 사람의 의도가 중요하다.</p>
<p>보편적으로 자주 사용하는, 크게 레이아웃을 이루는 태그로 정리했다.
<br />
(이미지는 내가 만들었다,,🍀)
<br /></p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/1644288d-d8ab-47a1-b216-aa89b9fe27da/image.png" /></p>
<h3 id="header">header</h3>
<p><code>&lt;header&gt;</code> : 문서 상단에 위치하며, 일반적으로 로고나 제목, 메뉴 같은 걸 담고 있는 도입부</p>
<h3 id="aside">aside</h3>
<p><code>&lt;aside&gt;</code> : 부가적인 정보나 보조 콘텐츠. 아티클 내부에서 쓰일 수도, 위의 이미지처럼 전역 사이드 콘텐츠로 쓰일 수도 있다.</p>
<h3 id="main">main</h3>
<p><code>&lt;main&gt;</code> : 사이트의 본격적인 내용으로 페이지에서 한 번만 사용 가능</p>
<h3 id="footer">footer</h3>
<p><code>&lt;footer&gt;</code> : 문서 하단에 위치하며, 일반적으로 연락처나 관련 정보를 담고 있음
<br />
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/4744ab8e-0755-4700-921f-bffe18c5c8df/image.png" /></p>
<h3 id="nav">nav</h3>
<p><code>&lt;nav&gt;</code> : 현재 문서 내부 또는 다른 문서로의 탐색 링크(메뉴, 목차 등)를 제공. 
<code>&lt;nav&gt;</code>로 묶을 땐 보통 안에 <code>&lt;ul&gt;</code> 태그로 리스트를 구성해 작업했다.
<br />
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/05e912bb-2755-41f0-b957-f0e5a3338469/image.png" /></p>
<h3 id="article">article</h3>
<p><code>&lt;article&gt;</code> : 하나의 완성된, 독립적인 내용을 나타내는 영역</p>
<h3 id="section">section</h3>
<p><code>&lt;section&gt;</code> : 관련된 주제로 묶은 영역 단위
<br />
🌠 고정된 규칙이 있는건 아니지만, 나는 위의 이미지처럼 <code>&lt;section&gt;</code>을 하나의 주제를 묶기 위한 UI 구역, <code>&lt;article&gt;</code>을 독립된 콘텐츠, 컴포넌트 단위로 보고 사용했다.</p>
<p>e.g.)</p>
<pre><code>&lt;section&gt;
  &lt;h2&gt;뉴스&lt;/h2&gt;
  &lt;article&gt;
    &lt;h3&gt;오늘의 주요 소식&lt;/h3&gt;
    &lt;p&gt;...&lt;/p&gt;
  &lt;/article&gt;
  &lt;article&gt;
    &lt;h3&gt;정치 뉴스&lt;/h3&gt;
    &lt;p&gt;...&lt;/p&gt;
  &lt;/article&gt;
&lt;/section&gt;</code></pre><p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/ca62759a-c446-493e-b0dc-62f532a5011c/image.png" /></p>
<h3 id="h1h6">h1~h6</h3>
<p><code>&lt;h1&gt;</code> ~ <code>&lt;h6&gt;</code> : 6개 레벨의 섹션 제목 <code>&lt;h1&gt;</code>가장 높은 섹션 레벨 <code>&lt;h6&gt;</code>가장 낮은 섹션 레벨
<br /><br /></p>
<h2 id="✅-텍스트-콘텐츠text-content">✅ 텍스트 콘텐츠(Text content)</h2>
<h3 id="ul-ol-li">ul, ol, li</h3>
<p><code>&lt;ul&gt;</code> : 순서가 없는 항목 (unordered list)
<code>&lt;ol&gt;</code> : 순서가 있는 항목 (ordered list)
<code>&lt;li&gt;</code> : 목록의 항목 리스트 (list item). 부모 요소인 ul, ol의 자식</p>
<h3 id="dl-dt-dd">dl, dt, dd</h3>
<p><code>&lt;dl&gt;</code> : 설명 목록 전체를 감싸는 태그
<code>&lt;dt&gt;</code> : 설명 목록의 제목
<code>&lt;dd&gt;</code> : 제목에 대한 설명</p>
<h3 id="figure-figcaption">figure, figcaption</h3>
<p><code>&lt;figure&gt;</code> : 이미지
<code>&lt;figcaption&gt;</code> : <code>&lt;figure&gt;</code>에 대한 설명</p>
<h3 id="p-pre">p, pre</h3>
<p><code>&lt;p&gt;</code> : 단락
<code>&lt;pre&gt;</code> : 서식을 유지한 텍스트 (들여쓰기, 줄바꿈 포함 등)
<br /></p>
<h2 id="✅-인라인-텍스트inline-text-semantics">✅ 인라인 텍스트(Inline text semantics)</h2>
<h3 id="b-strong">b, strong</h3>
<p><code>&lt;b&gt;</code> : <strong>굵은 글씨</strong>. 단순 시각적 강조 (의미 없음)
<code>&lt;strong&gt;</code> : <strong>굵은 글씨</strong>. 의미 있는 강조. 스크린 리더가 강조해서 읽기때문에 의미있는 곳에 사용해야한다.</p>
<h3 id="em-i">em, i</h3>
<p><code>&lt;em&gt;</code> : <em>의미 있는 기울임(강조)</em>
<code>&lt;i&gt;</code> : <em>기울임 글씨</em></p>
<h3 id="s-u-q">s, u, q</h3>
<p><code>&lt;s&gt;</code> : <del>취소선</del>
<code>&lt;i&gt;</code> : <u>밑줄</u>
<code>&lt;q&gt;</code> : <q>따옴표. 인라인 인용문</q></p>
<h3 id="subsup">sub,sup</h3>
<p><code>&lt;sub&gt;</code> : <sub>아래첨자</sub>
<code>&lt;sup&gt;</code> : <sup>윗첨자</sup></p>
<h3 id="time-code">time, code</h3>
<p><code>&lt;time&gt;</code> : 날짜/시간 정보를 표현. SEO와 접근성에 도움
<code>&lt;code&gt;</code> : <code>코드 텍스트</code>
<br /></p>
<p>등등...
</p>
<hr />
<h2 id="끝으로">끝으로</h2>
<p>과거의 나는, 보여지는 화려한 기능 구현에만 급급했다. 이후에 대규모 자사 서비스 운영을 하며 겪은 경험을 통해 새로운 인사이트를 발견했다. 의미 있는 구조 작성은 사용자 경험을 위해 지켜야 할 기본 원칙이고, 좋은 사용자 경험은 겉으로 드러나지 않는 작은 요소들까지 신경 쓰는 데서 시작되는 것. 😀
앞으로 접근성이나 성능 최적화같은 주제를 중심으로 개인적인 생각들을 자유롭게 기록해 볼 예정이다!</p>
<hr />
<h2 id="참고자료">참고자료</h2>
<p><a href="https://www.w3schools.com/html/default.asp">https://www.w3schools.com/html/default.asp</a>
<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements">https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements</a>
<a href="https://yozm.wishket.com/magazine/detail/2495/">https://yozm.wishket.com/magazine/detail/2495/</a></p>