<h2 id="✅-dom">✅ DOM</h2>
<blockquote>
<p>Document Object Model(문서 객체 모델)의 약자
웹 페이지에 나타나는 <strong>HTML 문서 전체를 객체로 표현한 것</strong></p>
</blockquote>
<p>이때 각 객체를 노드(Node)라는 용어로 표현하고, 태그는 요소 노드, 문자는 텍스트 노드로 구분된다.</p>
<p>HTML의 작은 부분까지 접근할 수 있고 DOM을 이용해 HTML로 구성된 웹페이지를 동적으로 움직이게 만들 수 있다.
<br /></p>
<p>🌠 <strong>log는 값 자체에, dir은 객체의 속성에 . . .</strong>
log와 dir 메소드의 가장 큰 차이는 DOM 객체를 다룰 때다.
DOM구조를 조회할 때에는 <code>console.dir</code>이 유용하다.
<br /></p>
<table>
<thead>
<tr>
<th>구분</th>
<th>log</th>
<th>dir</th>
</tr>
</thead>
<tbody><tr>
<td>기능</td>
<td>값을 그대로 출력<br />(콘솔에서 값 자체를 확인)</td>
<td>객체를 트리 구조로 출력<br />(객체의 속성들을 살펴보고 싶다면)</td>
</tr>
<tr>
<td>주 용도</td>
<td>변수 값, 문자열, 숫자 등 일반 출력</td>
<td>객체의 속성 구조 탐색</td>
</tr>
<tr>
<td>출력</td>
<td>객체를 내용+타입 정보를 함께</td>
<td>객체를 트리처럼</td>
</tr>
<tr>
<td>DOM 객체 출력</td>
<td>요소의 HTML 형태</td>
<td>요소의 JS 객체 속성</td>
</tr>
</tbody></table>
<p><br /><br /></p>
<h2 id="✅-dom-트리">✅ DOM 트리</h2>
<blockquote>
<p>HTML의 계층 구조는 DOM에서도 반영되는데 이러한 계층구조를 나무에 비유해서 DOM 트리라고 부른다.</p>
</blockquote>
<p>각 노드 간의 관계는 부모, 자식, 형제라는 용어로 표현한다.</p>
<p><br /><br /></p>
<h2 id="✅-node">✅ Node</h2>
<blockquote>
<p>DOM 안에서 하나의 단위(요소)를 뜻하는 말</p>
</blockquote>
<p>웹 페이지를 구성하는 모든 것 (태그, 텍스트, 주석 등)
<br /></p>
<p>e.g.) 이 경우 DOM 트리 구조는 . .</p>
<pre><code class="language-html">&lt;body&gt;
  &lt;h1&gt;Hello&lt;/h1&gt;
&lt;/body&gt;</code></pre>
<p>document <code>(Document Node)</code> &gt; 
body <code>(Element Node)</code> &gt; h1 <code>(Element Node)</code> &gt; 
Hello <code>(Text Node)</code>
<br /><br /></p>
<h2 id="✅-dom-이동-시-활용-가능한-프로퍼티">✅ DOM 이동 시 활용 가능한 프로퍼티</h2>
<br />

<h4 id="element">element</h4>
<table>
<thead>
<tr>
<th>프로퍼티</th>
<th>유형</th>
<th>결과</th>
</tr>
</thead>
<tbody><tr>
<td><strong>element.children</strong></td>
<td>자식 요소 노드</td>
<td>element의 자식 요소 모음 (HTMLCollection)</td>
</tr>
<tr>
<td><strong>element.firstElementChild</strong></td>
<td>자식 요소 노드</td>
<td>element의 첫 번째 자식 요소 하나</td>
</tr>
<tr>
<td><strong>element.lastElementChild</strong></td>
<td>자식 요소 노드</td>
<td>element의 마지막 자식 요소 하나</td>
</tr>
<tr>
<td><strong>element.parentElement</strong></td>
<td>부모 요소 노드</td>
<td>element의 부모 요소 하나</td>
</tr>
<tr>
<td><strong>element.previousElementSibling</strong></td>
<td>형제 요소 노드</td>
<td>element의 이전(previous) 혹은 <br />좌측(left)에 있는 요소 하나</td>
</tr>
<tr>
<td><strong>element.nextElementSibling</strong></td>
<td>형제 요소 노드</td>
<td>element의 다음(next) 혹은 <br />우측(right)에 있는 요소 하나</td>
</tr>
<tr>
<td><br /></td>
<td></td>
<td></td>
</tr>
</tbody></table>
<h4 id="node">node</h4>
<table>
<thead>
<tr>
<th>프로퍼티</th>
<th>유형</th>
<th>결과</th>
</tr>
</thead>
<tbody><tr>
<td><strong>node.childNodes</strong></td>
<td>자식 노드</td>
<td>node의 자식 노드 모음(NodeList)</td>
</tr>
<tr>
<td><strong>node.firstChild</strong></td>
<td>자식 노드</td>
<td>node의 첫 번째 자식 노드 하나</td>
</tr>
<tr>
<td><strong>node.lastChild</strong></td>
<td>자식 노드</td>
<td>node의 마지막 자식 노드 하나</td>
</tr>
<tr>
<td><strong>node.parentNode</strong></td>
<td>부모 노드</td>
<td>node의 부모 요소 하나</td>
</tr>
<tr>
<td><strong>node.previousSibling</strong></td>
<td>형제 노드</td>
<td>node의 이전(previous) 혹은 좌측(left)에 있는 노드 하나</td>
</tr>
<tr>
<td><strong>node.nextSibling</strong></td>
<td>형제 노드</td>
<td>node의 다음(next) 혹은 우측(right)에 있는 노드 하나</td>
</tr>
<tr>
<td><br /><br /></td>
<td></td>
<td></td>
</tr>
</tbody></table>
<h2 id="✅-주요-요소-노드-프로퍼티">✅ 주요 요소 노드 프로퍼티</h2>
<br />

<table>
<thead>
<tr>
<th>프로퍼티</th>
<th>내용</th>
<th>참고사항</th>
</tr>
</thead>
<tbody><tr>
<td><strong>element.innerHTML</strong></td>
<td>요소 노드 내부의 HTML코드 문자열로 리턴</td>
<td>요소 안의 정보를 확인할 수도 있지만, 내부의 HTML 자체를 수정할 때 좀 더 자주 활용</td>
</tr>
<tr>
<td><strong>element.outerHTML</strong></td>
<td>요소 노드 자체의 전체적인 HTML 코드를 문자열로 리턴</td>
<td>outerHTML은 새로운 값을 할당하면 요소 자체가 교체되어 버리기 때문에 주의</td>
</tr>
<tr>
<td><strong>element.textConten</strong>t</td>
<td>요소 노드 내부의 내용들 중에서 HTML을 제외하고 텍스트만 리턴</td>
<td>textContent는 말그대로 텍스트만 다루기 때문에HTML태그를 쓰더라도 모두 텍스트로 처리됨</td>
</tr>
<tr>
<td><br /><br /></td>
<td></td>
<td></td>
</tr>
</tbody></table>
<h2 id="✅-요소-노드-다루기">✅ 요소 노드 다루기</h2>
<br />

<table>
<thead>
<tr>
<th>프로퍼티</th>
<th>내용</th>
</tr>
</thead>
<tbody><tr>
<td><strong>document.createElement('태그이름')</strong></td>
<td>요소 노드 만들기</td>
</tr>
<tr>
<td><strong>element.textContent, element.innerHTML, ...</strong></td>
<td>요소 노드 꾸미기</td>
</tr>
<tr>
<td><strong>element.prepend, element.append, <br />element.after, element.before</strong></td>
<td>요소 노드 추가/이동</td>
</tr>
<tr>
<td><strong>element.remove()</strong></td>
<td>요소 노드 삭제</td>
</tr>
<tr>
<td><br /><br /></td>
<td></td>
</tr>
</tbody></table>
<h2 id="✅-html-속성-다루기">✅ HTML 속성 다루기</h2>
<p>표준 속성이 아닌 경우에는 프로퍼티로 변환이 안 되는데, 아래 메소드를 활용하면 표준이 아닌 HTML 속성들도 다룰 수 있다.
<br /></p>
<table>
<thead>
<tr>
<th>프로퍼티</th>
<th>내용</th>
</tr>
</thead>
<tbody><tr>
<td><strong>element.getAttribute('속성')</strong></td>
<td>속성에 접근하기</td>
</tr>
<tr>
<td><strong>element.setAttribute('속성', '값')</strong></td>
<td>속성 추가(수정)하기</td>
</tr>
<tr>
<td><strong>element.removeAttribute('속성')</strong></td>
<td>속성 제거하기</td>
</tr>
<tr>
<td><br /><br /></td>
<td></td>
</tr>
</tbody></table>
<h2 id="✅-스타일-다루기">✅ 스타일 다루기</h2>
<p>자바스크립트로 태그의 스타일을 다루는 방법</p>
<ol>
<li>style 프로퍼티 활용하기: <code>element.style.styleName = 'value';</code></li>
<li>class 변경을 통해 간접적으로 스타일 적용하기: <code>element.className</code>, <code>element.classList</code></li>
</ol>
<h3 id="classlist의-유용한-메소드">classList의 유용한 메소드</h3>
<table>
<thead>
<tr>
<th>메소드</th>
<th>내용</th>
<th>참고사항</th>
</tr>
</thead>
<tbody><tr>
<td><strong>classList.add</strong></td>
<td>클래스 추가</td>
<td>여러 개의 값을 전달하면 여러 클래스 추가 가능</td>
</tr>
<tr>
<td><strong>classList.remove</strong></td>
<td>클래스 삭제</td>
<td>여러 개의 값을 전달하면 여러 클래스 삭제 가능</td>
</tr>
<tr>
<td><strong>classList.toggle</strong></td>
<td>클래스 없으면 추가, <br />있으면 삭제하기</td>
<td>하나의 값만 적용 가능하고, <br />두 번째 파라미터로 추가 또는 삭제 기능을 강제할 수 있음</td>
</tr>
</tbody></table>
<p><br /><br /></p>
<h2 id="✅-태그-선택">✅ 태그 선택</h2>
<table>
<thead>
<tr>
<th>메소드</th>
<th>의미/결과</th>
</tr>
</thead>
<tbody><tr>
<td><strong>document.getElementById('id')</strong></td>
<td>id 선택</td>
</tr>
<tr>
<td><strong>document.getElementsByClassName('class')</strong></td>
<td>class 선택</td>
</tr>
<tr>
<td><strong>document.getElementsByTagName('tag')</strong></td>
<td>tag 선택</td>
</tr>
<tr>
<td><strong>document.querySelector('css')</strong></td>
<td>태그 선택 (가장 첫번째 태그 하나)</td>
</tr>
<tr>
<td><strong>document.querySelectorAll('css')</strong></td>
<td>태그 선택 (선택한 태그 전체 모음(NodeList))</td>
</tr>
</tbody></table>
<br />

<hr />
<h2 id="참고자료">참고자료</h2>
<p>코드잇 | 인터랙티브 자바스크립트</p>