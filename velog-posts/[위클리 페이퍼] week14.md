<h3 id="week14-위클리-페이퍼">week14 위클리 페이퍼</h3>
<ul>
<li>리액트만 사용할 때와 비교해 Next.js를 사용하는 이유에 대해 설명해 주세요.</li>
<li>Next.js에서 SSR을 실행하는 과정과 hydration에 대해 설명해 주세요.</li>
</ul>
<br />

<hr />
<br />

<h3 id="💬-리액트만-사용할-때와-비교해-nextjs를-사용하는-이유에-대해-설명해-주세요">💬 리액트만 사용할 때와 비교해 Next.js를 사용하는 이유에 대해 설명해 주세요.</h3>
<h4 id="리액트만-사용할-때의-한계">리액트만 사용할 때의 한계</h4>
<ul>
<li>클라이언트 렌더링(CSR)이 기본</li>
<li>서버로부터 렌더링에 필요한 파일을 다운 받는 시간이 소요되므로 초기 로딩이 느릴 수 있음</li>
<li>SEO 최적화 어려움</li>
<li>라우팅, 코드 분할, API 통합 등은 직접 구현해야 함</li>
</ul>
<blockquote>
<p>이러한 리액트의 단점을 보완하기 위해 나온 프레임워크 중 하나가 <code>Next.js</code>입니다.</p>
</blockquote>
<br />

<h4 id="nextjs를-사용하는-이유">Next.js를 사용하는 이유</h4>
<ul>
<li>서버 사이드 렌더링 (SSR) 지원</li>
<li>서버에서 HTML을 생성해 초기 로딩 속도 개선</li>
<li>SEO 최적화에 유리</li>
<li>정적 사이트 생성 (SSG): 빌드 시 HTML을 만들어 빠른 페이지 로딩 제공하며 서버 리소스 부담이 없음</li>
<li>파일 기반 라우팅 시스템으로 라우터 설정 없이 <code>pages/</code> 폴더 안에 파일을 만들면 자동으로 라우팅 처리로 가독성과 유지보수에 용이해짐</li>
<li>API Routes: 별도의 백엔드 서버 없이도 폼 전송과 인증, 데이터 처리 등 가능</li>
<li>이미지 최적화: <code>&lt;Image&gt;</code> 컴포넌트 제공<br />

</li>
</ul>
<p>📄 <strong>관련 게시글</strong>
<a href="https://velog.io/@iamsuuya/%EB%8D%B0%EC%9D%BC%EB%A6%AC-%ED%8C%80%EB%AF%B8%EC%85%98-Next.js-Next.js-image-%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8-%ED%94%84%EB%A6%AC%EB%A0%8C%EB%8D%94%EB%A7%81">https://velog.io/@iamsuuya/데일리-팀미션-Next.js-Next.js-image-컴포넌트-프리렌더링</a></p>
<br />

<hr />
<br />

<h3 id="💬-nextjs에서-ssr을-실행하는-과정과-hydration에-대해-설명해-주세요">💬 Next.js에서 SSR을 실행하는 과정과 hydration에 대해 설명해 주세요.</h3>
<h4 id="ssr이란">SSR이란?</h4>
<blockquote>
<p>Next.js에서 SSR(서버사이드 렌더링)은 사용자의 요청이 들어오면 서버에서 페이지에 필요한 데이터를 가져와 완전한 HTML 페이지를 생성한 후 브라우저로 전송하여 화면을 렌더링합니다. </p>
</blockquote>
<br />

<h4 id="ssr-실행-과정">SSR 실행 과정</h4>
<ol>
<li><p><strong>사용자 요청</strong>
사용자가 브라우저에서 특정 페이지(URL)를 요청</p>
</li>
<li><p><strong>프론트 서버 응답</strong>
<code>Next.js</code> 서버가 요청을 수신</p>
</li>
<li><p><strong>데이터 페칭</strong>
서버는 필요한 모든 데이터를 백엔드 서버나 API에 요청하여 가져옴</p>
</li>
<li><p><strong>HTML 렌더링</strong>
서버는 받아온 데이터를 활용해 해당 페이지에 대한 HTML을 생성</p>
</li>
<li><p><strong>HTML과 스크립트 전송</strong>
서버는 완성된 HTML 페이지와 클라이언트에서 동작할 스크립트(React 코드)를 브라우저로 전송</p>
</li>
<li><p><strong>브라우저 렌더링</strong>
브라우저는 전송받은 HTML을 즉시 렌더링하여 사용자에게 보여줌
이로 인해 초기 페이지 로딩 속도가 매우 빠름</p>
</li>
<li><p><strong>Hydration</strong>
Hydration 단계 시작</p>
</li>
</ol>
<br />

<h4 id="hydration이란">Hydration이란?</h4>
<blockquote>
<p>서버에서 미리 렌더링된 HTML을 브라우저가 받아 React의 자바스크립트 코드와 연결하는 과정입니다.
Hydration이 완료돼야 페이지가 완전히 상호작용 가능해집니다.</p>
</blockquote>
<p>📄 <strong>관련 게시글</strong>
<a href="https://velog.io/@iamsuuya/%EB%8D%B0%EC%9D%BC%EB%A6%AC-%ED%8C%80%EB%AF%B8%EC%85%98-Next.js-TTV-TTI-hydration-%EC%BD%94%EB%93%9C%EC%8A%A4%ED%94%8C%EB%A6%AC%ED%8C%85">https://velog.io/@iamsuuya/데일리-팀미션-Next.js-TTV-TTI-hydration-코드스플리팅</a></p>