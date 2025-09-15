<h3 id="915월">9.15(월)</h3>
<ul>
<li>Next.js의 Middleware는 언제, 왜 사용하나요?</li>
<li>SEO를 개선하기 위해 Next.js에서 사용할 수 있는 방법은 무엇인가요?</li>
</ul>
<br />

<hr />
<br />

<h3 id="💬-nextjs의-middleware는-언제-왜-사용하나요">💬 Next.js의 Middleware는 언제, 왜 사용하나요?</h3>
<h4 id="middleware란">Middleware란?</h4>
<blockquote>
<p>클라이언트의 요청(Request)을 서버가 처리해서 응답(Response)을 보내는 과정 중에 그 중간에서 실행되는 로직을 미들웨어라고 부릅니다.</p>
</blockquote>
<h4 id="middleware의-역할">Middleware의 역할</h4>
<p>미들웨어는 클라이언트의 요청을 서버가 처리하기 전에 요청을 가로채서 미리 필터링하거나, 필요한 데이터의 추가적인 처리를 하는 등의 작업을 수행하는 역할을 하는데요.</p>
<h4 id="middleware가-필요한-이유">Middleware가 필요한 이유</h4>
<ol>
<li>페이지 렌더링 전에 인증을 확인하거나 요청을 확인,</li>
<li>요청 데이터를 사전에 처리하거나 특정 API요청을 수행하거나 캐시를 관리,</li>
<li>요청에 대한 응답을 변환하거나 에러를 처리할 수 있다.<br />
</li>
</ol>
<ul>
<li><strong>사용자 인증 및 접근 제어</strong>
(사용자 로그인 여부 확인이나 특정 페이지 접근 권한 검사, 보호 페이지 접근 전 인증, 특정 IP 주소에서만 접근을 허용할 때)</li>
<li><strong>요청 헤더/쿠키 수정</strong>
(쿠키를 추가, 수정 또는 제거하거나, 응답 데이터를 변경해 개인화된 콘텐츠를  제공할 때)</li>
<li><strong>페이지 리디렉션</strong>
(요청 경로에 따라 다른 페이지로 리다이렉트 할 때)</li>
<li><strong>API 요청 전처리</strong>
(특정 API 요청이 서버에 도달하기 전 필요한 데이터를 사건 처리하거나 다른 API 호출을 수행할 때)</li>
<li>캐시된 페이지보다 먼저 수행되어 정적 파일과 페이지를 개인화할 수 있음</li>
</ul>
<p>등 요청 처리 전 필요한 로직을 수행할 때 사용합니다.</p>
<br />

<hr />
<br />

<h3 id="💬-seo를-개선하기-위해-nextjs에서-사용할-수-있는-방법은-무엇인가요">💬 SEO를 개선하기 위해 Next.js에서 사용할 수 있는 방법은 무엇인가요?</h3>
<p><code>Next.js</code>는 <code>SEO</code>에 필요한 다양한 기능을 제공하고 있는데요.
<br /></p>
<h4 id="1-정적-사이트-생성ssg-및-서버-사이드-렌더링ssr">1. 정적 사이트 생성(SSG) 및 서버 사이드 렌더링(SSR)</h4>
<p><code>Next.js</code>는 SSG와 SSR을 모두 지원해 SEO 최적화에 유리합니다. </p>
<ul>
<li><p><strong>SSG(정적 사이트 생성)</strong> : 빠른 로딩, 일관된 콘텐츠 제공
빌드 시점에 미리 HTML을 생성 
<u>검색 엔진 크롤러가 미리 준비된 HTML을 쉽게 인식하고 색인할 수 있어 검색엔진 최적화에 유리합니다.</u></p>
</li>
<li><p><strong>SSR(서버 사이드 렌더링)</strong> : 실시간 데이터 포함한 SEO 대응
사용자의 요청이 있을 때마다 서버에서 HTML을 동적으로 생성
<u>서버에서 렌더링된 HTML이 전달되어 검색 엔진 크롤러의 인식에 유리합니다. </u></p>
</li>
</ul>
<h4 id="2-동적-라우팅">2. 동적 라우팅</h4>
<p><code>Next.js</code>의 동적 라우팅 기능을 사용하면 URL 경로를 자유롭게 설계할 수 있는데요. 
검색 엔진은 URL 내 키워드를 분석해서 페이지 주제를 파악합니다. 
콘텐츠를 카테고리, 태그, 키워드 기반으로 정리해 크롤러가 사이트 구조를 더 잘 이해하기 때문에 SEO에 효과적인 구조를 만들 수 있습니다.</p>
<h4 id="3-메타-태그-설정">3. 메타 태그 설정</h4>
<p><code>Next.js</code>에서는 <code>&lt;Head&gt;</code> 컴포넌트를 사용해 각 페이지마다 메타 정보를 쉽게 설정할 수 있습니다.</p>
<h4 id="4-사이트맵-및-로봇-파일robotstxt-설정">4. 사이트맵 및 로봇 파일(robots.txt) 설정</h4>
<p>사이트맵은 검색 엔진이 사이트의 구조를 이해하고 모든 페이지를 크롤링하는 데 도움을 줍니다.
<code>Next.js</code>에서는 <code>next-sitemap</code>패키지를 통해 자동으로 사이트맵을 생성할 수 있습니다.</p>
<h4 id="5-이미지-최적화-nextimage">5. 이미지 최적화 (next/image)</h4>
<p><code>Next.js</code>의 Image 컴포넌트는 이미지 자동 최적화, 지연 로딩, 크기 조정 등의 기능을 제공합니다.
이미지 로딩 속도 향상은 사용자 경험과 SEO에 긍정적인 영향을 줍니다.
<a href="https://velog.io/@iamsuuya/%EB%8D%B0%EC%9D%BC%EB%A6%AC-%ED%8C%80%EB%AF%B8%EC%85%98-Next.js-Next.js-image-%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8-%ED%94%84%EB%A6%AC%EB%A0%8C%EB%8D%94%EB%A7%81">https://velog.io/@iamsuuya/데일리-팀미션-Next.js-Next.js-image-컴포넌트-프리렌더링</a></p>
<br />

<hr />
<p>📄 <strong>참고 자료(출처)</strong>
<a href="https://doubled.tistory.com/120">https://doubled.tistory.com/120</a></p>