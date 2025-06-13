<p>HTML에서 폼 요소로 쓰이는 다양한 인풋과 속성, 폼 전송 타입을 정리해봤다.
아무래도 자주 사용하지 않으면 쉽게 잊혀지기 마련이라 잘 정리해서 필요할 때마다 꺼내보려고 작성했다. </p>
<p>(내가 자주 까먹음..)
<br /><br /></p>
<h2 id="✅-자주-사용하는-인풋-타입과-속성">✅ 자주 사용하는 인풋 타입과 속성</h2>
<h3 id="텍스트-text">텍스트 (text)</h3>
<pre><code>&lt;style&gt;
  input::placeholder {
    color: #dddddd;
  }
&lt;/style&gt;
&lt;!-- placeholder: 값이 채워지기 전 보여주는 값 --&gt;
&lt;input name=&quot;name&quot; type=&quot;text&quot; placeholder=&quot;이름&quot;&gt;
&lt;!-- required: 필수 입력 값 --&gt;
&lt;input name=&quot;name&quot; type=&quot;text&quot; required&gt;
&lt;!-- autocomplete: 자동 완성 --&gt;
&lt;input name=&quot;name&quot; type=&quot;text&quot; autocomplete=&quot;on&quot;&gt;
  &lt;!-- e.g.) 사용에 따라 값을 채워 넣을 수도 있다. --&gt;
  &lt;input name=&quot;email&quot; type=&quot;email&quot; autocomplete=&quot;email&quot;&gt;
  &lt;input name=&quot;telephone&quot; autocomplete=&quot;tel&quot;&gt;</code></pre><br />

<h3 id="글-textarea">글 (textarea)</h3>
<pre><code>&lt;textarea name=&quot;content&quot;&gt;&lt;/textarea&gt;</code></pre><br />

<h3 id="숫자-number">숫자 (number)</h3>
<h4 id="·-기본">· 기본</h4>
<pre><code>&lt;input type=&quot;number&quot;&gt;</code></pre><h4 id="·-min-max-step">· min, max, step</h4>
<pre><code>&lt;!-- 100에서 1000사이, 버튼을 눌렀을 때 100씩 증가, 감소 --&gt;
&lt;input type=&quot;number&quot; min=&quot;100&quot; max=&quot;1000&quot; step=&quot;100&quot;&gt;</code></pre><br />

<h3 id="이메일-email">이메일 (email)</h3>
<pre><code>&lt;input name=&quot;email&quot; type=&quot;email&quot;&gt;</code></pre><br />

<h3 id="비밀번호-password">비밀번호 (password)</h3>
<pre><code>&lt;input type=&quot;password&quot;&gt;</code></pre><br />

<h3 id="옵션-선택-select">옵션 선택 (select)</h3>
<pre><code>&lt;label for=&quot;genre&quot;&gt;장르&lt;/label&gt;
&lt;select id=&quot;genre&quot; name=&quot;genre&quot;&gt;
  &lt;option value=&quot;korean&quot;&gt;한국 영화&lt;/option&gt;
  &lt;option value=&quot;foreign&quot;&gt;외국 영화&lt;/option&gt;
  &lt;option value=&quot;drama&quot;&gt;드라마&lt;/option&gt;
  &lt;option value=&quot;documentary&quot;&gt;다큐멘터리&lt;/option&gt;
  &lt;option value=&quot;vareity&quot;&gt;예능&lt;/option&gt;
&lt;/select&gt;</code></pre><br />

<h3 id="체크박스-checkbox">체크박스 (checkbox)</h3>
<h4 id="·-한-개-항목-선택-시">· 한 개 항목 선택 시</h4>
<pre><code>&lt;label&gt;
  &lt;input name=&quot;agreement&quot; type=&quot;checkbox&quot;&gt;
  동의
&lt;/label&gt;</code></pre><h4 id="·-여러-항목-선택-시">· 여러 항목 선택 시</h4>
<pre><code>&lt;label for=&quot;film&quot;&gt;좋아하는 영화 장르&lt;/label&gt;
&lt;label&gt;
  &lt;input type=&quot;checkbox&quot; name=&quot;film&quot; value=&quot;action&quot;&gt;
  액션
&lt;/label&gt;
&lt;label&gt;
  &lt;input type=&quot;checkbox&quot; name=&quot;film&quot; value=&quot;comedy&quot;&gt;
  코미디
&lt;/label&gt;
&lt;label&gt;
  &lt;input type=&quot;checkbox&quot; name=&quot;film&quot; value=&quot;romance&quot;&gt;
  로맨스
&lt;/label&gt;</code></pre><br />

<h3 id="라디오-radio">라디오 (radio)</h3>
<pre><code>&lt;input id=&quot;very-bad&quot; name=&quot;feeling&quot; value=&quot;0&quot; type=&quot;radio&quot;&gt;
&lt;label for=&quot;very-bad&quot;&gt;아주 나쁨&lt;/label&gt;
&lt;input id=&quot;bad&quot; name=&quot;feeling&quot; value=&quot;1&quot; type=&quot;radio&quot;&gt;
&lt;label for=&quot;bad&quot;&gt;나쁨&lt;/label&gt;
&lt;input id=&quot;soso&quot; name=&quot;feeling&quot; value=&quot;2&quot; type=&quot;radio&quot;&gt;
&lt;label for=&quot;soso&quot;&gt;보통&lt;/label&gt;
&lt;input id=&quot;good&quot; name=&quot;feeling&quot; value=&quot;3&quot; type=&quot;radio&quot;&gt;
&lt;label for=&quot;good&quot;&gt;좋음&lt;/label&gt;
&lt;input id=&quot;very-good&quot; name=&quot;feeling&quot; value=&quot;4&quot; type=&quot;radio&quot;&gt;
&lt;label for=&quot;very-good&quot;&gt;아주 좋음&lt;/label&gt;</code></pre><br />

<h3 id="날짜-date">날짜 (date)</h3>
<pre><code>&lt;input name=&quot;birthdate&quot; type=&quot;date&quot;&gt;</code></pre><br />

<h3 id="파일-file">파일 (file)</h3>
<h4 id="·-기본-1">· 기본</h4>
<pre><code>&lt;input name=&quot;avatar&quot; type=&quot;file&quot;&gt;</code></pre><h4 id="·-파일-형식">· 파일 형식</h4>
<pre><code>&lt;input name=&quot;avatar&quot; type=&quot;file&quot; accept=&quot;.png,.jpg&quot;&gt;</code></pre><h4 id="·-파일-개수">· 파일 개수</h4>
<pre><code>&lt;!-- multiple: 여러 개 선택 가능 --&gt;
&lt;input name=&quot;photos&quot; type=&quot;file&quot; multiple&gt;</code></pre><br />

<h3 id="범위-range">범위 (range)</h3>
<pre><code>&lt;label for=&quot;signup-feeling&quot;&gt;현재 기분&lt;/label&gt;
&lt;input id=&quot;signup-feeling&quot; name=&quot;feeling&quot; min=&quot;1&quot; max=&quot;10&quot; type=&quot;range&quot;&gt;</code></pre><p><br /><br /></p>
<p>** + 라벨 (label) 인풋 포커싱 **</p>
<pre><code>&lt;label&gt;
  아이디
  &lt;input name=&quot;...&quot;&gt;
&lt;/label&gt;

&lt;label for=&quot;username&quot;&gt;아이디&lt;/label&gt;
&lt;input id=&quot;username&quot; name=&quot;...&quot;&gt;</code></pre><br />

<p>** 🌠이 외 더 많은 속성 값 참고 링크**
HTTP attribute: autocomplete: <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Attributes/autocomplete">https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Attributes/autocomplete</a>
<br /><br /></p>
<h2 id="✅-폼-전송-방법">✅ 폼 전송 방법</h2>
<h3 id="codeactioncode-속성"><code>action</code> 속성</h3>
<p>폼 데이터를 제출할 때 현재 페이지 주소(기본값) 말고 다른 주소(URL)로 지정하여 연결하고 싶다면 <code>&lt;form&gt;</code> 태그의 <code>action</code> 속성을 사용한다.</p>
<pre><code>&lt;!DOCTYPE html&gt;
&lt;html&gt;
  ...
  &lt;body&gt;
      // action=&quot;https://google.com/search&quot;
    // action=&quot;/login&quot;
    // action=&quot;submit.php&quot;
    &lt;form action=&quot;https://google.com/search&quot;&gt;
      &lt;input name=&quot;search&quot;&gt;
      &lt;button&gt;검색&lt;/button&gt;
    &lt;/form&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><br />

<h3 id="codemethodcode-속성"><code>method</code> 속성</h3>
<p>페이지 이동 또는 데이터 전송 시 서버에 리퀘스트 라는 걸 보내는데, 리퀘스트의 종류에는 <code>GET</code> 방식과 <code>POST</code> 방식이 있다.</p>
<h4 id="get">GET</h4>
<p><code>method</code>의 기본 속성 값은 <code>GET</code>.
<strong>GET 리퀘스트는 데이터를 요청/조회(받기/가져오기)한다.</strong>
폼 버튼을 눌렀을 때 페이지를 이동하는 것은 웹 브라우저가 어떤 서버로 <code>GET</code> 리퀘스트를 보낸 것.  쉽게 말해 사용자가 웹페이지를 요청할 때, URL에 필요한 데이터를 함께 포함해 요청하는 것.</p>
<p>URL에 데이터가 노출 되는게 특징이다. 
e.g.) <code>?key=value</code> </p>
<p><code><a href="http://127.0.0.0:5000/?email=html%40code.kr&amp;password=1234&amp;password_repeat=1234">http://127.0.0.0:5000/?email=html%40code.kr&amp;password=1234&amp;password_repeat=1234</a></code> </p>
<p><s style="color: #999999;">물음표 이후 폼에 입력한 value 값이 들어가 있는데, 이런걸 쿼리 문자열(Query String)이라고 한다. 인풋 태그마다 name 속성 값이랑 입력한 값이 짝지어 적혀있다.</s>
<br /></p>
<p>하지만! </p>
<p>파일을 업로드 하는 경우, 파일은 크기가 크기 때문에 <code>GET</code>방식과 쿼리 문자열만으로 보낼 수는 없다. 이럴 때 <code>POST</code>를 주로 사용한다.
<strong>POST 리퀘스트는 데이터를 제출/전송(보내기)한다.</strong></p>
<h4 id="post">POST</h4>
<p>회원가입, 로그인, 작성, 파일 업로드 등 사용자 입력 데이터를 전송할 때 사용되며,
URL에 데이터가 노출되지않아 비교적 보안에 유리하고, 전송 데이터 양의 제한이 거의 없기 때문에 대용량 데이터 전송이 가능하다.</p>
<pre><code>&lt;!DOCTYPE html&gt;
&lt;html&gt;
  ...
  &lt;body&gt;
    &lt;form method=&quot;post&quot;&gt;
        &lt;label for=&quot;profile&quot;&gt;프로필&lt;/label&gt;
        &lt;input id=&quot;profile&quot; name=&quot;profile&quot; type=&quot;file&quot;&gt;
      &lt;/div&gt;
      &lt;button&gt;확인&lt;/button&gt;
    &lt;/form&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre><br />


<hr />
<h2 id="참고자료">참고자료</h2>
<p>Codeit 토픽
<a href="https://developer.mozilla.org/ko/">https://developer.mozilla.org/ko/</a>
<a href="https://developer.mozilla.org/ko/docs/Web/HTML/Reference/Elements/form">https://developer.mozilla.org/ko/docs/Web/HTML/Reference/Elements/form</a></p>