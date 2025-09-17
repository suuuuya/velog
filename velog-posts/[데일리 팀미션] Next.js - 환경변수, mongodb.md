<h3 id="917수">9/17(수)</h3>
<ul>
<li>환경변수란 무엇인지 설명해주세요.</li>
<li>아래 코드는 mongodb 연결을 위한 코드입니다. 빈 칸에 어떤 코드가 들어가야 할까요? 또한 정상적으로 연결이 되었다면 <code>console.log</code>는 어떤 결과를 출력할까요?<pre><code class="language-tsx">export default [    ] function handler(req,res) {
      [    ] dbConnect();
      console.log(mongoose.connection.readyState);
}</code></pre>
<br />

</li>
</ul>
<hr />
<br />

<h3 id="💬-환경변수란-무엇인지-설명해주세요">💬 환경변수란 무엇인지 설명해주세요.</h3>
<h4 id="환경변수environement-variable">환경변수(Environement Variable)</h4>
<blockquote>
<p>프로그램 실행 환경에 따라 달라지는 값을 설정할 수 있도록 도와주는 변수</p>
</blockquote>
<p>API 키, 서버 URL, 데이터베이스 연결 정보처럼 민감하거나 환경에 따라 달라질 수 있는 값들을 코드에 직접 노출하지 않고 안전하게 관리하기 위해 사용합니다.</p>
<h4 id="장점">장점</h4>
<ul>
<li>보안 유지</li>
<li>환경별 설정 분리
(개발, 테스트, 운영 환경마다 다른 값을 적용 가능)</li>
<li>코드 재사용성 향상
(하나의 코드베이스로 다양한 환경에 대응 가능)</li>
</ul>
<br />

<h4 id="nextjs에서-환경변수-사용하기">Next.js에서 환경변수 사용하기</h4>
<p>Next.js는 환경변수를 기본 지원합니다.</p>
<p><code>.env.local</code> 파일을 추가해 환경변수를 정의하고 사용할 수 있습니다.</p>
<pre><code class="language-tsx"># .env.local
NEXT_PUBLIC_API_URL=https://myapi.com
MY_SECRET_KEY=abcdef123456</code></pre>
<p>🌠 <code>NEXT_PUBLIC_</code>를 접두사가 붙은 변수는 브라우저에서도 접근 가능하고, 접두사가 없는 변수는 서버 사이드에서만 접근 가능합니다.</p>
<pre><code class="language-tsx">// 클라이언트 / 서버 모두 가능 (NEXT_PUBLIC이 붙은 경우)
console.log(process.env.NEXT_PUBLIC_API_URL);
// 서버 사이드에서만 가능
console.log(process.env.MY_SECRET_KEY);</code></pre>
<br />

<hr />
<br />

<h3 id="💬-아래-코드는-mongodb-연결을-위한-코드입니다-빈-칸에-어떤-코드가-들어가야-할까요-또한-정상적으로-연결이-되었다면-consolelog는-어떤-결과를-출력할까요">💬 아래 코드는 mongodb 연결을 위한 코드입니다. 빈 칸에 어떤 코드가 들어가야 할까요? 또한 정상적으로 연결이 되었다면 <code>console.log</code>는 어떤 결과를 출력할까요?</h3>
<h4 id="async-await">async, await</h4>
<pre><code class="language-tsx">export default [  async  ] function handler(req,res) {
        [  await  ] dbConnect();
        console.log(mongoose.connection.readyState);
}</code></pre>
<p>빈 칸에 들어갈 코드는 <code>async</code>, <code>await</code>입니다.</p>
<p><code>dbConnect()</code> 함수가 비동기 함수이기 때문에 db 연결이 완료될 때까지 기다려서 정확한 연결 상태를 확인하기 위해 <code>async</code>, <code>await</code>를 사용합니다.</p>
<p>(<code>async</code>, <code>await</code>은 비동기 함수의 실행이 끝날 때까지 기다린 후에 그 다음 코드를 순차적으로 실행하게 만드는 역할)</p>
<h4 id="출력-값-1">출력 값 1</h4>
<p>그리고 정상적으로 접속된 상태라면 <code>connected(정상적으로 연결됨)</code> 라는 뜻의<code>1</code>이라는 값을 출력합니다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/d5fdc926-3121-4e12-96cd-6827c41ae64b/image.png" /></p>
<p>이 외에 다른 <code>mongoose.connection.readyState</code> 상태 값에는</p>
<p>0 = disconnected(연결되지 않음)
2 = connecting(연결 중)
3 = disconnecting (연결 끊는 중)</p>
<p>으로 접속 상태를 확인할 수 있습니다.</p>
<p><a href="https://mongoosejs.com/docs/api/connection.html#Connection.prototype.readyState">Mongoose | Connection.prototype.readyState 문서</a></p>