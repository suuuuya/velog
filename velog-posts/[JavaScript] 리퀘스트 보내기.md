<blockquote>
<p>유튜브에서 좋아요 버튼을 누르면 좋아요 개수가 1개 올라가고, 인스타그램에서 아래로 스크롤을 하면 새로운 콘텐츠가 로딩된다. </p>
</blockquote>
<p>이런 식으로 <strong>페이지를 새로고침 하지 않고</strong> <code>fetch</code> 함수와 <code>axios</code>라는 라이브러리를 사용해서 <strong>서버와 데이터를 주고 받는 방법</strong>에 대해 자세히 알아보자.
<br /></p>
<p>아니 지금 스프린트 미션 작업하면서 이 학습 내용 같이 정리하고 있었는데 딱 마침 로그인/회원가입 POST 요청 보내는 요구사항이 나와서 소룸 . . . ! 🤷🏻‍♀️
<br /><br /></p>
<h2 id="✅-ajax">✅ AJAX</h2>
<blockquote>
<p><strong>A</strong>synchronous(비동기) <strong>J</strong>avaScript(자바스크립트) <strong>A</strong>nd <strong>X</strong>ML의 약자</p>
</blockquote>
<p>☑️ 예전에는 외부로 데이터를 주고받을 때 XML이라는 형식을 많이 사용해서 이런 이름이 붙었지만 지금은 <code>JSON</code> 형식을 많이 사용한다.</p>
<br />

<p>✔️ 자바스크립트를 이용해 서버와 비동기적으로 통신하고,
✔️ 페이지 새로고침 없이 데이터를 가져오거나 보낼 수 있는 기술
<br /></p>
<p>쉽게 말해, <strong>웹페이지를 새로고침하지 않고도 서버에서 데이터를 받아와 화면을 업데이트하는 기술</strong>을 말한다.</p>
<p><br /><br /><br /></p>
<h2 id="✅-fetch">✅ fetch</h2>
<blockquote>
<p>브라우저에 내장된 비동기 HTTP 요청 함수</p>
</blockquote>
<p>✔️ Promise 기반으로 작성되어 가독성이 좋다.</p>
<br />

<h3 id="fetch-기본-문법">fetch() 기본 문법</h3>
<pre><code class="language-js">const res = await fetch(url);

// 리스폰스 상태 코드
res.status;

// 리스폰스 헤더
res.headers;

// 리스폰스 바디
await res.json(); // JSON 문자열을 파싱해서 자바스크립트 객체로 변환
await res.text(); // 문자열을 그대로 가져옴
</code></pre>
<br />

<h4 id="fetch-사용-예시">fetch() 사용 예시</h4>
<pre><code class="language-js">const res = await fetch('https://learn.codeit.kr/api/color-surveys');
const data = await res.json();
console.log(data);


------------------------------------------------
  {
  count: 51,
  next: 'https://learn.codeit.kr/api/color-surveys/?offset=10&amp;limit=10',
  previous: null,
  results: [
    {
      createdAt: 1688448542000,
      updatedAt: 1688448542000,
      colorCode: '#FFFFFF',
      id: 51,
      mbti: 'ENTJ'
    },
    {
      createdAt: 1688448539000,
      updatedAt: 1688448539000,
      colorCode: '#FFFFFF',
      id: 50,
      mbti: 'ENTJ'
    },
    ...
  ]
}</code></pre>
<br />

<h4 id="url-객체">URL 객체</h4>
<p>쿼리 파라미터를 보낼 때는 URL 객체를 사용할 수 있다.</p>
<pre><code class="language-js">const params = { offset: 10, limit: 10 };
const url = new URL('https://learn.codeit.kr/api/color-surveys');
Object.keys(params).forEach((key) =&gt; url.searchParams.append(key, params[key]));
const res = await fetch(url);
const data = await res.json();
console.log(data);</code></pre>
<p><br /><br /></p>
<h3 id="fetch-옵션">fetch() 옵션</h3>
<p>리퀘스트 설정을 할 수 있다.</p>
<ul>
<li><p>method(메소드): 
'GET', 'POST', 'PATCH', 'DELETE' 같은 값으로 설정할 수 있다.
method를 설정하지 않으면 기본 값이 'GET'.</p>
</li>
<li><p>headers(헤더): 
자주 설정하는 헤더로는 'Content-Type'가 있다.</p>
</li>
<li><p>body(바디): 자바스크립트 객체는 그대로 전달할 수 없기 때문에 JSON 문자열로 바꿔 줘야 한다.</p>
</li>
</ul>
<p>🌠 <strong>참고</strong>
<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/fetch#parameters">이 외 모든 옵션 | MDN 문서</a></p>
<br />

<h4 id="post-리퀘스트-예시">POST 리퀘스트 예시</h4>
<pre><code class="language-js">const surveyData = {
  mbti: 'ENFP',
  colorCode: '#ABCDEF',
    password: '0000',
};

const res = fetch('https://learn.codeit.kr/api/color-surveys', { 
  method: 'POST' ,
  body: JSON.stringify(surveyData),
  headers: {
    'Content-Type': 'application/json',
  },
});
const data = await res.json();
console.log(data);


------------------------------------------
{
  createdAt: 1688477153992,
  updatedAt: 1688477153992,
  colorCode: '#ABCDEF',
  id: 52,
  mbti: 'ENFP',
  password: '0000'
}</code></pre>
<p><br /><br /></p>
<h3 id="api-함수-만들기">API 함수 만들기</h3>
<p>똑같은 리퀘스트를 보내는 코드가 반복된다면 함수로 만들어 주는 것이 좋다.
웹 개발을 할 때 API를 호출하는 함수들을 따로 모아 두고 필요할 때 import해서 쓴다고 함.</p>
<p>📄 *<em>api.js *</em>
리퀘스트마다 바뀔 수 있는 부분을 함수 파라미터 받아서 활용하자.</p>
<pre><code class="language-js">export async function getColorSurveys(params = {}) {
  const url = new URL('https://learn.codeit.kr/api/color-surveys');
  Object.keys(params).forEach((key) =&gt;
    url.searchParams.append(key, params[key])
  );
  const res = await fetch(url);
  const data = await res.json();
  return data;
}

export async function getColorSurvey(id) {
  const res = await fetch(`https://learn.codeit.kr/api/color-surveys/${id}`);
  const data = await res.json();
  return data;
}

export async function createColorSurvey(surveyData) {
  const res = await fetch('https://learn.codeit.kr/api/color-surveys', {
    method: 'POST',
    body: JSON.stringify(surveyData),
    headers: {
      'Content-Type': 'application/json',
    },
  });
  const data = await res.json();
  return data;
}</code></pre>
<p><br /><br /></p>
<h3 id="fetch-오류-처리">fetch() 오류 처리</h3>
<p>리퀘스트를 보낼 때 발생하는 오류는 크게 두 가지가 있다.</p>
<p>✔️ URL이 이상하거나 헤더 정보가 이상해서 리퀘스트 자체가 실패하는 경우
✔️ 리퀘스트는 성공적이지만 상태 코드가 실패를 나타내는 경우(4XX, 5XX)</p>
<br />
fetch() 함수는 첫 번째 경우에만 리턴하는 Promise를 rejectg한다. 

<p>따라서 fetch()에 대한 오류 처리를 할 때는 언제 Promise가 reject되는지, 어떤 내용이 리스폰스 바디로 돌아오는지를 잘 생각해야 하는데,
fetch() 오류를 깔끔하게 처리하는 방법은 두 번째 경우에도 오류를 throw하는 것. </p>
<p>리스폰스 상태 코드의 성공 여부: .ok 프로퍼티로 확인</p>
<pre><code class="language-js">export async function getColorSurvey(id) {
  const res = await fetch(`https://learn.codeit.kr/api/color-surveys/${id}`);

  if (!res.ok) {
    throw new Error('데이터를 불러오는데 실패했습니다.');
  }

  const data = await res.json();
  return data;
}</code></pre>
<p>리퀘스트가 완전히 성공하지 않는 이상 오류를 throw하기 때문에 쉽게 처리할 수 있다.</p>
<p>🌠  여기서 리퀘스트가 완전히 성공한다는 건, 리퀘스트가 잘 전달되고 리스폰스도 성공을 나타내는 상황을 말한다.</p>
<pre><code class="language-js">import { getColorSurvey } from './api.js';

try {
  const data = await getColorSurvey(1234); // 존재하지 않는 id
  console.log(data);
} catch (e) {
  console.log('오류가 발생했습니다:')
  console.log(e.message);
}


-----------------------------------
오류가 발생했습니다:
데이터를 불러오는 데 실패했습니다.</code></pre>
<p><br /><br /></p>
<h2 id="✅-axios-문법">✅ axios 문법</h2>
<blockquote>
<p>Promise 기반의 HTTP 클라이언트 라이브러리</p>
</blockquote>
<p>✔️ fetch보다 다양한 기능 제공</p>
<p>axios는 HTTP 메소드 이름과 동일한 메소드를 사용하고 리스폰스 바디를 data 프로퍼티로 접근할 수 있다.</p>
<br />

<h4 id="설치">설치</h4>
<pre><code class="language-bash">npm install axios</code></pre>
<br />

<h3 id="get-리퀘스트">GET 리퀘스트</h3>
<pre><code class="language-js">// axios
async function getColorSurvey(id) {
  const res = await axios.get(`https://learn.codeit.kr/api/color-surveys/${id}`);
  return res.data;
}

-----------------------------------------------------------------------

// fetch
async function getColorSurvey(id) {
  const res = await fetch(`https://learn.codeit.kr/api/color-surveys/${id}`);
  const data = await res.json();
  return data;
}
</code></pre>
<br />

<p>쿼리 파라미터를 보낼 경우 params 옵션을 사용한다.</p>
<pre><code class="language-js">// axios
export async function getColorSurveys(params = {}) {
  const res = await axios.get('https://learn.codeit.kr/api/color-surveys', {
    params,
  });
  return res.data;
}

-----------------------------------------------------

// fetch
async function getColorSurveys(params = {}) {
  const url = new URL('https://learn.codeit.kr/api/color-surveys');
  Object.keys(params).forEach((key) =&gt;
    url.searchParams.append(key, params[key])
  );
  const res = await fetch(url);
  const data = await res.json();
  return data;
}

</code></pre>
<br />
params 외에 헤더 같은 정보도 옵션으로 설정할 수 있다.

<p>🌠** 참고 자료: **<a href="https://axios-http.com/docs/req_config">axios 문서</a>
<br /><br /></p>
<h3 id="post-리퀘스트">POST 리퀘스트</h3>
<p>리퀘스트에 보낼 바디 내용은 두 번째 아규먼트로 전달하면 된다. 
그리고 자바스크립트 객체를 문자열로 변환하지 않고 그대로 전달할 수 있다.</p>
<pre><code class="language-js">// axios
async function createColorSurvey(surveyData) {
  const res = await axios.post('https://learn.codeit.kr/api/color-surveys', surveyData);
  return res.data;
}

---------------------------------------------------

// fetch
async function createColorSurvey(surveyData) {
  const res = await fetch('https://learn.codeit.kr/api/color-surveys', {
    method: 'POST',
    body: JSON.stringify(surveyData),
    headers: {
      'Content-Type': 'application/json',
    },
  });

  if (!res.ok) {
    throw new Error('데이터를 생성하는데 실패했습니다.');
  }

  const data = await res.json();
  return data;
}
</code></pre>
<p>리퀘스트에.. 
바디가 필요 없는 get이나 delete는 옵션을 두 번째 아규먼트로 받고, 
바디가 필요한 post, patch, put은 바디 데이터를 두 번째 아규먼트로 받고, 옵션을 세 번째 아규먼트로 받는다.
<br /><br /></p>
<h3 id="axios-인스턴스">axios 인스턴스</h3>
<p>리퀘스트마다 공통되는 부분이 있으면 인스턴스를 생성하고 인스턴스로 리퀘스트를 보낸다.</p>
<pre><code class="language-js">const instance = axios.create({
  baseURL: 'https://learn.codeit.kr/api',
  timeout: 3000,
});

async function getColorSurveys(params = {}) {
  const res = await instance.get(`/color-surveys`, {
    params,
  });
  return res.data;
}
</code></pre>
<p>인스턴스를 만들 때 설정할 수 있는 옵션은 리퀘스트를 보낼 때 설정할 수 있는 옵션과 똑같다.
<br /><br /></p>
<h3 id="axios-오류-처리">axios 오류 처리</h3>
<p>axios는 리퀘스트 자체가 실패하거나 리스폰스의 상태 코드가 실패(4XX, 5XX)를 나타내면 Promise를 reject 한다. 
두 번째 경우는 리스폰스가 돌아온 것이기 때문에 이걸 에러 객체에 전달한다. 
그래서 에러를 처리할 때 에러 리스폰스에 접근할 수 있다.</p>
<h4 id="📄-apijs">📄 api.js</h4>
<pre><code class="language-js">export async function createColorSurvey(surveyData) {
  const res = await axios.post('https://learn.codeit.kr/api/color-surveys', surveyData);
  return res.data;
}
</code></pre>
<h4 id="📄-mainjs">📄 main.js</h4>
<pre><code class="language-js">import { createColorSurvey } from './api.js';

const surveyData = {
  mbti: 'EEEE',
  colorCode: '#CDCDCD',
  password: '0000',
};

try {
  const newColorSurvey = await createColorSurvey(surveyData);
  console.log(newColorSurvey);
} catch (e) {
  if (e.response) { 
    // 리퀘스트는 성공했지만 상태 코드가 실패(4XX, 5XX)를 나타냄
    console.log(e.response.status);
    console.log(e.response.data);
  } else { 
    // 리퀘스트 자체가 실패
    console.log('리퀘스트가 실패했습니다.');
  }
}


-----------------------------
Invalid MBTI</code></pre>
<p><br /><br /></p>
<h2 id="✅-fetch와-axios">✅ fetch와 axios</h2>
<br />

<h3 id="공통점">공통점</h3>
<p>✔️ 비동기 HTTP 요청 가능
✔️ Promise 기반
✔️ GET, POST, PUT, DELETE 등 REST API 호출 가능
<br /></p>
<h3 id="차이점">차이점</h3>
<table>
<thead>
<tr>
<th>비교</th>
<th>fetch</th>
<th>axios</th>
</tr>
</thead>
<tbody><tr>
<td>지원</td>
<td>브라우저 내장</td>
<td>별도 설치 필요</td>
</tr>
<tr>
<td>응답 처리</td>
<td>res.json() 호출 필요</td>
<td>res.data 바로 사용</td>
</tr>
<tr>
<td>JSON 자동 변환</td>
<td>수동</td>
<td>자동 변환</td>
</tr>
<tr>
<td>등...</td>
<td></td>
<td></td>
</tr>
<tr>
<td><br /></td>
<td></td>
<td></td>
</tr>
</tbody></table>
<h3 id="요약">요약</h3>
<p>✔️ fetch =&gt; 브라우저 내장 간단한 요청 함수
✔️ axios =&gt; 기능 풍부한 외부 라이브러리
<br /></p>
<table>
<thead>
<tr>
<th>항목</th>
<th>fetch</th>
<th>axios</th>
</tr>
</thead>
<tbody><tr>
<td><strong>장점</strong></td>
<td>가벼움, 설치 불필요</td>
<td>기능 풍부, 코드 간결</td>
</tr>
<tr>
<td><strong>단점</strong></td>
<td>기능 제한, JSON 변환 필요</td>
<td>설치 필요, 파일 크기 증가</td>
</tr>
<tr>
<td><strong>추천 상황</strong></td>
<td>간단한 요청</td>
<td>복잡한 API 호출, 에러 처리, 인터셉터 필요</td>
</tr>
</tbody></table>
<br />

<hr />
<h2 id="참고자료">참고자료</h2>
<p>코드잇 | 자바스크립트 리퀘스트 보내기 토픽</p>