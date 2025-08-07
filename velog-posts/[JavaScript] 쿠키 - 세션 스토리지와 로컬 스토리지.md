<h2 id="✅-쿠키">✅ 쿠키</h2>
<blockquote>
<p>웹사이트 접속 시 사용자의 컴퓨터(브라우저)에 저장되는 작은 텍스트 파일</p>
</blockquote>
<p>이를 통해 웹사이트는 사용자의 웹 브라우저를 식별하고,</p>
<ul>
<li>로그인 정보 유지</li>
<li>장바구니 정보</li>
<li>방문 기록 분석</li>
</ul>
<p>등과 같은 정보를 저장한다.</p>
<p>이런 정보를 통해 개인 맞춤화 된 웹 경험을 제공하거나, 웹사이트 운영 및 마케팅 전략을 개선하는 데 사용된다.</p>
<p>쿠키는 웹사이트 간에도 전송될 수 있기 때문에, 보안상의 취약점이 발생할 수 있다.
이를 방지하기 위한 방법 중 하나가 <code>sameSite</code> 속성이다.
<br /></p>
<h3 id="🌠-samesite">🌠 sameSite</h3>
<p>쿠키에는 여러 속성이 있는데, </p>
<blockquote>
<p>sameSite 속성은 <strong>웹사이트 간 요청</strong>에서 전송될 수 있는지 여부를 설정한다.</p>
</blockquote>
<p>즉, 다른 도메인에서 요청할 때 쿠키를 보낼지 말지 결정하는 보안 설정이다.</p>
<p>sameSite 속성에는 세 가지 종류가 있다.</p>
<h4 id="samesitelax">sameSite=Lax</h4>
<ul>
<li>기본 보안 수준(기본값)</li>
<li>사용자가 링크 클릭으로 사이트를 이동한 경우에만 쿠키를 전송한다.</li>
</ul>
<h4 id="samesitestrict">sameSite=Strict</h4>
<ul>
<li>오직 같은 사이트 내에서만 쿠키가 전송된다(가장 보안이 강함)</li>
<li>다른 사이트에서 들어오는 모든 요청에는 쿠키를 전송하지 않는다.</li>
</ul>
<h4 id="samesitenone">sameSite=None</h4>
<ul>
<li>다른 사이트에서의 모든 요청에도 쿠키 전송을 허용한다.</li>
<li>단, 보안 강화를 위해 반드시 Secure 속성과 함께 설정해야하며, HTTPS 환경에서만 동작한다.</li>
</ul>
<p><br /><br /></p>
<h3 id="기타-알아두면-좋은-attribute">기타 알아두면 좋은 Attribute</h3>
<h4 id="httponly">HttpOnly</h4>
<p><code>HttpOnly</code>를 사용하면 쿠키를 자바스크립트로 사용하지 못하게 막을 수 있다.</p>
<h4 id="secure">Secure</h4>
<p><code>Secure</code>를 지정하면 Https 리퀘스트를 보낼 때만 쿠키를 보낸다.</p>
<h4 id="expires와-max-age">Expires와 Max-Age</h4>
<p>쿠키의 수명을 지정하는 속성</p>
<ul>
<li>Expires: 만료 시기 지정</li>
<li>Max-Age: 쿠키 수명 지정<br />

</li>
</ul>
<p>☑️ <strong>세션 쿠키(Session Cookie)</strong>는 <code>Expires</code>나 <code>Max-Age</code>를 지정하지 않으면 만들 수 있다.
세션 쿠키: 브라우저를 닫으면 지워지는 쿠키
☑️ <strong>영속적인 쿠키(Persistent Cookie)</strong>는 <code>Expires</code>나 <code>Max-Age</code>로 수명을 지정해서 만들 수 있다.
수명이 다하면 지워지는 쿠키</p>
<p><br /><br /></p>
<h3 id="사용법">사용법</h3>
<h4 id="서버에서-리스폰스할-때">서버에서 리스폰스할 때</h4>
<p>서버에서 <code>set-cookie</code> 헤더를 리스폰스로 보내주면 웹 브라우저는 알아서 쿠키 값을 저장해 둔다.
<code>Set-Cookie: session-id=1234; Domain=codeit.kr; Path=/; HttpOnly; Secure; SameSite=Strict; Max-Age=2592000;</code></p>
<ul>
<li><code>session-id</code>: 쿠키의 key 값</li>
<li><code>1234</code>: 벨류 값</li>
<li><code>domain</code>, <code>path</code>,<code>samesite</code>... : 쿠키의 attribute 값<br />

</li>
</ul>
<h4 id="클라이언트에서-보낼-때">클라이언트에서 보낼 때</h4>
<p>리퀘스트를 보낼 때 주소에 해당하는 쿠키가 저장되어 있다면 웹 브라우저가 알아서 쿠키를 보내준다.</p>
<p><code>Cookie: session-id=1234; Domain=codeit.kr; Path=/; HttpOnly; Secure; SameSite=Strict; Max-Age=2592000;</code></p>
<h4 id="자바스크립트로-사용하기">자바스크립트로 사용하기</h4>
<p>보통은 서버가 쿠키 값을 만들고, 클라이언트에서는 웹 브라우저에 맡기고 건드리지 않는 것이 권장된다.
하지만, 클라이언트에서 자바스크립트로 쿠키를 <code>생성/수정/참조</code> 할 수도 있다.</p>
<ul>
<li><p>추가, 수정하는 코드
<code>document.cookie = &quot;session-id=1234; Domain=codeit.kr; Path=/; HttpOnly; Secure; SameSite=Strict; Max-Age=2592000;&quot;;</code></p>
</li>
<li><p>값 지우기
<code>Max-Age</code> 값을 0으로 업데이트하면 지워짐.
<code>document.cookie = &quot;session-id; Max-Age: 0;&quot;;</code></p>
<br />

</li>
</ul>
<hr />
<br />

<h2 id="✅-세션-스토리지와-로컬-스토리지">✅ 세션 스토리지와 로컬 스토리지</h2>
<blockquote>
<p>웹 브라우저에서 데이터를 저장하는 데 사용되는 두 가지 저장소 유형</p>
</blockquote>
<p>둘의 주요 차이점은 데이터 지속성에 있다.</p>
<p>❗️ <u>두 저장소 모두 클라이언트 측에 데이터를 저장하므로 중요한 정보나 민감한 정보는 저장하지 않는 것이 좋다.</u></p>
<h3 id="쿠키와-다른-점">쿠키와 다른 점</h3>
<p>🌠 <strong>쿠키를 사용하면 브라우저에서 데이터를 저장할 수 있는데, 왜 또 다른 객체를 사용해서 데이터를 저장하는 걸까?</strong></p>
<ul>
<li>클라이언트가 만들고 관리하는 데이터</li>
<li>쿠키보다 사용할 수 있는 용량이 크다.</li>
<li>자바스크립트로 편리하게 조작할 수 있다.</li>
<li>만료 기간이 없다.
<br /><br /></li>
</ul>
<h3 id="📂-세션-스토리지sessionstorage">📂 세션 스토리지(SessionStorage)</h3>
<h4 id="특징">특징</h4>
<ul>
<li>현재 탭에서만 유효한 저장소</li>
<li>탭을 닫으면 데이터가 사라진다.(비영구적)</li>
<li>다른 탭과 데이터는 공유되지 않는다.</li>
</ul>
<h4 id="🌠-사용-예시">🌠 사용 예시</h4>
<p>폼 입력 값, 현재 페이지 데이터 등</p>
<pre><code class="language-js">// 값을 저장하는 코드. (이미 값이 있다면) 수정하는 코드
const data = inputElement.value;
sessionStorage.setItem('draft', data);

// 값을 참조해서 사용할 때
const draftData = sessionStorage.getItem('draft');

// 값 지우기
sessionStorage.removeItem('draft');</code></pre>
<p><br /><br /></p>
<h3 id="📂-로컬-스토리지localstorage">📂 로컬 스토리지(LocalStorage)</h3>
<h4 id="특징-1">특징</h4>
<ul>
<li>해당 사이트에서 유효한 저장소</li>
<li>탭을 닫거나 브라우저를 닫아도 데이터가 유지된다.(영구적)</li>
<li>여러 탭 사이에서도 데이터가 공유된다.</li>
</ul>
<h4 id="🌠-사용-예시-1">🌠 사용 예시</h4>
<p>로그인 정보, 설정, 즐겨찾기 등</p>
<pre><code class="language-js">// 사용자가 사이드바 감추기 버튼을 클릭했을 때
// 값을 저장, 수정
localStorage.setItem('show-sidebar', 'false');

// 사용자가 처음 접속했을 때
const showSidebar = localStorage.getItem('show-sidebar') === 'true';

// 값 지우기
localStorage.removeItem('show-sidebar');</code></pre>
<p><br /><br /></p>
<h3 id="스토리지가-변경되었을-때-처리하기">스토리지가 변경되었을 때 처리하기</h3>
<pre><code class="language-js">window.addEventListener(&quot;storage&quot;, () =&gt; {
  const showSidebar = localStorage.getItem('show-sidebar') === 'true';
    // showSidebar 값 적용하기
});</code></pre>
<p><a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/storage_event">Window storage evt - Web APIs | MDN</a></p>
<p><br /><br /></p>
<h3 id="🌠-활용-사례">🌠 활용 사례</h3>
<h4 id="초안-임시-저장하기">초안 임시 저장하기</h4>
<p>텍스트를 입력하다 실수로 창을 닫아 버리더라도 내용이 남아있게 할 수 있다.
로컬 스토리지를 사용해 구현할 수 있다.</p>
<h4 id="웹-앱">웹 앱</h4>
<p>웹 기반으로 만들어진 프로그램(웹 앱)들은 세션, 로컬 스토리지를 사용한다.
예시) 피그마, 노션 등..</p>
<br />


<hr />
<h2 id="참고자료">참고자료</h2>
<p>코드잇 토픽</p>
<h3 id="참고하면-좋은-자료">참고하면 좋은 자료</h3>
<h4 id="쿠키">쿠키</h4>
<p><a href="https://developer.mozilla.org/ko/docs/Web/HTTP/Guides/Cookies">HTTP 쿠키 - HTTP|MDN</a>
<a href="https://blog.pumpkin-raccoon.com/80">리액트 쿠키 쉽게 사용하기</a></p>
<h4 id="웹-스토리지">웹 스토리지</h4>
<p><a href="https://developer.mozilla.org/ko/docs/Web/API/Web_Storage_API">Web Storage API | MDN</a>
<a href="https://web.dev/articles/storage-for-the-web?hl=ko">웹용 스토리지</a>
<a href="https://ko.javascript.info/localstorage">로컬 스토리지와 세션 스토리지</a></p>