<h3 id="916화">9.16(화)</h3>
<ul>
<li>Next.js에서 API Routes란 무엇인지 설명해주세요.</li>
<li>API Routes에서 req와 res 객체의 역할을 각각 설명해주세요.</li>
</ul>
<br />

<hr />
<br />

<h3 id="💬-nextjs에서-api-routes란-무엇인지-설명해주세요">💬 Next.js에서 API Routes란 무엇인지 설명해주세요.</h3>
<h4 id="nextjs의-api-routes">Next.js의 API Routes</h4>
<blockquote>
<p>Next.js 앱 내에서 서버리스 함수 형태로 작동하는 <strong>API 엔드포인트를 쉽게 만들 수 있는 기능</strong>입니다. </p>
</blockquote>
<p><code>pages/api</code> 폴더 안에 JavaScript 또는 TypeScript 파일을 생성하는 것만으로, 파일 하나당 하나의 API 엔드포인트가 자동으로 만들어집니다. </p>
<p>클라이언트는 이 <strong>엔드포인트에 HTTP 요청을 보내고</strong>, 서버는 요청을 처리한 후 <strong>응답을 반환</strong>합니다.</p>
<p>🔎 <strong>응답</strong>: 해당 API는 HTML 페이지 대신 JSON 데이터나 상태 코드를 반환합니다.
🔎 <strong>엔드포인트</strong>: 클라이언트와 서버가 통신할 때 사용하는 특정 ‘주소’ 또는 ‘경로’를 의미합니다. 쉽게 말해, 클라이언트가 서버에 요청을 보내기 위해 접속하는 URL 경로를 뜻합니다.</p>
<p><strong>별도의 백엔드 서버 없이도 클라이언트의 요청을 받아 <u>데이터베이스 조회, 사용자 요청 처리, 외부 서비스 연동 등 다양한 백엔드 작업을 수행할 수 있습니다.</u></strong></p>
<br />

<hr />
<br />

<h3 id="💬-api-routes에서-req와-res-객체의-역할을-각각-설명해주세요">💬 API Routes에서 req와 res 객체의 역할을 각각 설명해주세요.</h3>
<p>Next.js의 API Routes에서는 각 API 핸들러 함수가 <code>req</code>와 <code>res</code> 객체를 인자로 받아 요청과 응답을 처리하는데요.</p>
<pre><code class="language-tsx">export default function handler(req, res) {
  ...</code></pre>
<h4 id="reqrequest">req(Request)</h4>
<blockquote>
<p><code>req</code> 객체는 클라이언트의 HTTP <code>요청</code> 정보를 담고 있습니다.</p>
</blockquote>
<p>요청에 대한 다양한 정보(요청 메서드, URL 등)를 확인할 수 있습니다. </p>
<h4 id="주요-속성">주요 속성</h4>
<ul>
<li><code>req.method</code>: 요청 메서드(GET, POST, PUT 등)</li>
<li><code>req.query</code>: 쿼리 스트링 파라미터 (?id=123)</li>
<li><code>req.body</code>: POST/PUT 등의 body 데이터 (JSON, 폼 데이터 등)</li>
<li><code>req.headers</code>: 요청 헤더 정보</li>
</ul>
<br />

<h4 id="resresponse">res(Response)</h4>
<blockquote>
<p><code>res</code> 객체는 클라이언트에게 HTTP <code>응답</code>을 보내는 역할을 합니다. </p>
</blockquote>
<p>상태 코드 설정, JSON이나 텍스트 데이터 전송, 헤더 설정 등 클라이언트에 보낼 정보를 담아 응답을 마무리하는 데 사용됩니다.</p>
<h4 id="주요-메서드">주요 메서드</h4>
<ul>
<li><code>res.status(code)</code>: HTTP 상태 코드 설정</li>
<li><code>res.json(data)</code>: JSON 데이터 응답</li>
<li><code>res.send(data)</code>: 텍스트 응답</li>
<li><code>res.setHeader(key, value)</code>: 헤더 설정</li>
</ul>