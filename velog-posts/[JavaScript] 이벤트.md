<h2 id="✅-이벤트">✅ 이벤트</h2>
<blockquote>
<p>웹페이지에서 마우스를 클릭했을 때, 키를 입력했을 때, 특정요소에 포커스가 이동되었을 때 어떤 사건을 발생시키는 것 </p>
</blockquote>
<p><br /><br /></p>
<h2 id="✅-이벤트-핸들러">✅ 이벤트 핸들러</h2>
<h3 id="등록하기">등록하기</h3>
<h4 id="인라인-방식">인라인 방식</h4>
<pre><code class="language-html">&lt;div onclick=&quot;alert('1. 클릭했습니다.')&quot;&gt;클릭&lt;/div&gt;
&lt;div onclick=&quot;view()&quot;&gt;클릭&lt;/div&gt;

&lt;script&gt;
  function view() {
  alert(&quot;2. 클릭했습니다&quot;);
  }
&lt;/script&gt;</code></pre>
<br />

<h4 id="일반-방식">일반 방식</h4>
<h4 id="이벤트-리스너event-listener">이벤트 리스너(Event Listener)</h4>
<blockquote>
<p>이벤트를 기다렸다가(듣다가) 발생하면 지정한 함수(핸들러) 를 실행하는 것.</p>
</blockquote>
<p>addEventListener(이벤트 등록 메소드) 메소드 사용</p>
<pre><code class="language-js">// 첫 번째 인자: 이벤트 이름(종류)
// 두 번째 인자: 이벤트 발생 시 실행할 함수(콜백)
element.addEventListener('이벤트 종류', 함수);

// -------------------------------------------
// 이벤트 객체(Event Object)
// 이벤트 핸들러 함수는 실행될 때 자동으로 이벤트 객체를 전달받는다.

// 이벤트 타겟: button 
// 이벤트 타입: click, mouseenter
1.
const button = document.querySelector('button');
button.addEventListener('click', function(){
  alert('버튼을 클릭했습니다!');
});

2.
button.addEventListener(&quot;mouseenter&quot;, dehighlight);
function dehighlight(e) {
  e.currentTarget.style.backgroundColor = &quot;#cfa&quot;;
}

3.
document.addEventListener(&quot;dragover&quot;, (e) =&gt; {
  e.preventDefault();
});

...</code></pre>
<br />

<h3 id="삭제하기">삭제하기</h3>
<pre><code class="language-js">element.removeEventListener('type', handler);</code></pre>
<p><br /><br /></p>
<h2 id="✅-이벤트의-종류">✅ 이벤트의 종류</h2>
<h3 id="마우스-이벤트">마우스 이벤트</h3>
<table>
<thead>
<tr>
<th>이벤트 타입</th>
<th>설명</th>
</tr>
</thead>
<tbody><tr>
<td><strong>mousedown</strong></td>
<td>마우스 버튼을 누르는 순간</td>
</tr>
<tr>
<td><strong>mouseup</strong></td>
<td>마우스 버튼을 눌렀다 떼는 순간</td>
</tr>
<tr>
<td><strong>click</strong></td>
<td>왼쪽 버튼을 클릭한 순간</td>
</tr>
<tr>
<td><strong>dblclick</strong></td>
<td>왼쪽 버튼을 빠르게 두 번 클릭한 순간</td>
</tr>
<tr>
<td><strong>contextmenu</strong></td>
<td>오른쪽 버튼을 클릭한 순간</td>
</tr>
<tr>
<td><strong>mousemove</strong></td>
<td>마우스를 움직이는 순간</td>
</tr>
<tr>
<td><strong>mouseover</strong></td>
<td>마우스 포인터가 요소 위로 올라온 순간</td>
</tr>
<tr>
<td><strong>mouseout</strong></td>
<td>마우스 포인터가 요소에서 벗어나는 순간</td>
</tr>
<tr>
<td><strong>mouseenter</strong></td>
<td>마우스 포인터가 요소 위로 올라온 순간 (버블링이 일어나지 않음)</td>
</tr>
<tr>
<td><strong>mouseleave</strong></td>
<td>마우스 포인터가 요소에서 벗어나는 순간 (버블링이 일어나지 않음)</td>
</tr>
</tbody></table>
<p><br /><br /></p>
<h3 id="키보드-이벤트">키보드 이벤트</h3>
<table>
<thead>
<tr>
<th>이벤트 타입</th>
<th>설명</th>
</tr>
</thead>
<tbody><tr>
<td><strong>keydown</strong></td>
<td>키보드의 버튼을 누르는 순간</td>
</tr>
<tr>
<td><strong>keypress</strong></td>
<td>키보드의 버튼을 누르는 순간 <br />('a', '5' 등 출력이 가능한 키에서만 동작하며, Shift, Esc 등의 키에는 반응하지 않음)</td>
</tr>
<tr>
<td><strong>keyup</strong></td>
<td>키보드의 버튼을 눌렀다 떼는 순간</td>
</tr>
</tbody></table>
<p><br /><br /></p>
<h3 id="포커스-이벤트">포커스 이벤트</h3>
<table>
<thead>
<tr>
<th>이벤트 타입</th>
<th>설명</th>
</tr>
</thead>
<tbody><tr>
<td><strong>focusin</strong></td>
<td>요소에 포커스가 되는 순간</td>
</tr>
<tr>
<td><strong>focusout</strong></td>
<td>요소로부터 포커스가 빠져나가는 순간</td>
</tr>
<tr>
<td><strong>focus</strong></td>
<td>요소에 포커스가 되는 순간 (버블링이 일어나지 않음)</td>
</tr>
<tr>
<td><strong>blur</strong></td>
<td>요소로부터 포커스가 빠져나가는 순간 (버블링이 일어나지 않음)</td>
</tr>
</tbody></table>
<p><br /><br /></p>
<h3 id="폼입력-이벤트">폼/입력 이벤트</h3>
<table>
<thead>
<tr>
<th>이벤트 타입</th>
<th>설명</th>
</tr>
</thead>
<tbody><tr>
<td><strong>change</strong></td>
<td>입력된 값이 바뀌는 순간</td>
</tr>
<tr>
<td><strong>input</strong></td>
<td>값이 입력되는 순간</td>
</tr>
<tr>
<td><strong>select</strong></td>
<td>입력 양식의 하나가 선택되는 순간</td>
</tr>
<tr>
<td><strong>submit</strong></td>
<td>폼을 전송하는 순간</td>
</tr>
</tbody></table>
<p><br /><br /></p>
<h3 id="스크롤-이벤트">스크롤 이벤트</h3>
<table>
<thead>
<tr>
<th>이벤트 타입</th>
<th>설명</th>
</tr>
</thead>
<tbody><tr>
<td><strong>scroll</strong></td>
<td>스크롤 바가 움직일 때</td>
</tr>
</tbody></table>
<p><br /><br /></p>
<h3 id="로드-및-기타-이벤트">로드 및 기타 이벤트</h3>
<table>
<thead>
<tr>
<th>이벤트 타입</th>
<th>설명</th>
</tr>
</thead>
<tbody><tr>
<td>load</td>
<td>페이지의 로딩이 완료되었을 때 이벤트 발생</td>
</tr>
<tr>
<td>resize</td>
<td>윈도우 사이즈를 움직일 때 발생</td>
</tr>
<tr>
<td>abort</td>
<td>이미지의 로딩이 중단되었을 때 이벤트 발생</td>
</tr>
<tr>
<td>unload</td>
<td>페이지가 다른 곳으로 이동될 때 이벤트 발생</td>
</tr>
<tr>
<td>scroll</td>
<td>스크롤바를 움직였을 때 이벤트 발생</td>
</tr>
</tbody></table>
<p><br /><br /></p>
<h2 id="✅-이벤트-객체의-주요-프로퍼티">✅ 이벤트 객체의 주요 프로퍼티</h2>
<h3 id="공통-프로퍼티">공통 프로퍼티</h3>
<p>모든 이벤트 객체가 공통적으로 가지는 속성.</p>
<table>
<thead>
<tr>
<th>프로퍼티</th>
<th>설명</th>
</tr>
</thead>
<tbody><tr>
<td><strong>type</strong></td>
<td>이벤트 이름 ('click', 'mouseup', 'keydown' 등)</td>
</tr>
<tr>
<td><strong>target</strong></td>
<td>이벤트가 발생한 요소</td>
</tr>
<tr>
<td><strong>currentTarget</strong></td>
<td>이벤트 핸들러가 등록된 요소</td>
</tr>
<tr>
<td><strong>timeStamp</strong></td>
<td>이벤트 발생 시각(페이지가 로드된 이후부터 경과한 밀리초)</td>
</tr>
<tr>
<td><strong>bubbles</strong></td>
<td>버블링 단계인지를 판단하는 값</td>
</tr>
</tbody></table>
<p><br /><br /></p>
<h3 id="마우스-이벤트-1">마우스 이벤트</h3>
<p>마우스 관련 이벤트에서 사용할 수 있는 속성들.</p>
<table>
<thead>
<tr>
<th>프로퍼티</th>
<th>설명</th>
</tr>
</thead>
<tbody><tr>
<td><strong>button</strong></td>
<td>누른 마우스의 버튼 (0: 왼쪽, 1: 가운데(휠), 2: 오른쪽)</td>
</tr>
<tr>
<td><strong>clientX, clientY</strong></td>
<td>마우스 커서의 브라우저 표시 영역에서의 위치</td>
</tr>
<tr>
<td><strong>pageX, pageY</strong></td>
<td>마우스 커서의 문서 영역에서의 위치</td>
</tr>
<tr>
<td><strong>offsetX, offsetY</strong></td>
<td>마우스 커서의 이벤트 발생한 요소에서의 위치</td>
</tr>
<tr>
<td><strong>screenX, screenY</strong></td>
<td>마우스 커서의 모니터 화면 영역에서의 위치</td>
</tr>
<tr>
<td><strong>altKey</strong></td>
<td>이벤트가 발생할 때 alt키를 눌렀는지</td>
</tr>
<tr>
<td><strong>ctrlKey</strong></td>
<td>이벤트가 발생할 때 ctrl키를 눌렀는지</td>
</tr>
<tr>
<td><strong>shiftKey</strong></td>
<td>이벤트가 발생할 때 shift키를 눌렀는지</td>
</tr>
<tr>
<td><strong>metaKey</strong></td>
<td>이벤트가 발생할 때 meta키를 눌렀는지 <br />(window는 window키, mac은 cmd키)</td>
</tr>
</tbody></table>
<p><br /><br /></p>
<h3 id="키보드-이벤트-1">키보드 이벤트</h3>
<p>키보드 관련 이벤트에서 사용할 수 있는 속성들.</p>
<table>
<thead>
<tr>
<th>프로퍼티</th>
<th>설명</th>
</tr>
</thead>
<tbody><tr>
<td><strong>key</strong></td>
<td>누른 키가 가지고 있는 값</td>
</tr>
<tr>
<td><strong>code</strong></td>
<td>누른 키의 물리적인 위치</td>
</tr>
<tr>
<td><strong>altKey</strong></td>
<td>이벤트가 발생할 때 alt키를 눌렀는지</td>
</tr>
<tr>
<td><strong>ctrlKey</strong></td>
<td>이벤트가 발생할 때 ctrl키를 눌렀는지</td>
</tr>
<tr>
<td><strong>shiftKey</strong></td>
<td>이벤트가 발생할 때 shift키를 눌렀는지</td>
</tr>
<tr>
<td><strong>metaKey</strong></td>
<td>이벤트가 발생할 때 meta키를 눌렀는지 <br />(window는 window키, mac은 cmd키)</td>
</tr>
</tbody></table>
<br />

<p>🌠** 더 많은 프로퍼티 **
<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event">이벤트</a>
<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent">마우스 이벤트</a>
<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent">키보드 이벤트</a>
<br /><br /></p>
<h2 id="✅-버블링">✅ 버블링</h2>
<blockquote>
<p>이벤트가 자식 요소에서 부모 요소로 전파되는 현상</p>
</blockquote>
<p>이벤트 버블링 차단</p>
<pre><code class="language-js">event.stopPropagation();</code></pre>
<p><br /><br /></p>
<h2 id="✅-캡처링">✅ 캡처링</h2>
<blockquote>
<p>이벤트 전파의 첫 번째 단계 
이벤트가 가장 바깥쪽 요소부터 안쪽 요소로 전달되는 과정</p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/f1c41e0d-8645-42ed-8703-e292b337c04f/image.png" /></p>
<h4 id="예시">예시</h4>
<p>실행 순서:</p>
<ol>
<li>body의 캡처링 이벤트 리스너 실행</li>
<li>버튼의 클릭 이벤트 실행<pre><code class="language-js">document.body.addEventListener('click', function(){
console.log('body에서 캡처링');
}, true); // 세 번째 인자가 true면 캡처링 단계에서 실행
</code></pre>
</li>
</ol>
<p>document.getElementById('btn').addEventListener('click', function(){
  console.log('버튼 클릭');
});</p>
<pre><code>
### 이벤트 흐름
* 캡처링 단계: 이벤트가 하위 요소로 전파되는 단계
* 타깃 단계: 이벤트가 실제 타깃 요소에 전달되는 단계
* 버블링 단계: 이벤트가 상위 요소로 전파되는 단계

&lt;br&gt;

[표준 DOM 이벤트](https://www.w3.org/TR/uievents/) 
[자바스크립트의 이벤트 순서](https://www.quirksmode.org/js/events_order.html#link4) 
[addEventListner에 캡쳐링 단계 적용하기](https://developer.mozilla.org/ko/docs/Web/API/EventTarget/addEventListener) 

&lt;br&gt;&lt;br&gt;
## ✅ 이벤트 위임
&gt; **이벤트 버블링을 이용해 부모 요소에만 이벤트 핸들러를 등록**하고,
이벤트가 발생한 자식 요소를 구분하여 처리하는 방식.

✔️ 자식 요소 각각에 핸들러를 달지 않아도 된다.
✔️ 성능과 유지보수 측면에서 효율적이다.

#### 예시
예) ul 안에 여러 li가 있을 때, 각 li 클릭 시 실행

* 일반적인 방식

```js
// li 갯수만큼 핸들러가 등록됨.
const items = document.querySelectorAll('li');
items.forEach(item =&gt; {
  item.addEventListener('click', function(){
    console.log(this.textContent);
  });
});</code></pre><ul>
<li>이벤트 위임 방식<pre><code class="language-js">// 핸들러 1개만 등록
// 새로운 li가 동적으로 추가되어도 자동 적용 가능
const ul = document.querySelector('ul');
</code></pre>
</li>
</ul>
<p>ul.addEventListener('click', function(event){
  if(event.target.tagName === 'LI'){
    console.log(event.target.textContent);
  }
});</p>
<pre><code>
## ✅ 브라우저의 기본 동작
&gt;브라우저에는 각 태그별 혹은 상황별로 기본적으로 약속된 동작들이 있다.

e.g.) &lt;code&gt;a&lt;/code&gt; 태그 클릭 시, 페이지 이동이나 &lt;code&gt;form&lt;/code&gt; submit 시 페이지 새로고침 등

### 기본 동작 막기
이벤트 객체의 preventDefault() 메소드를 사용.
```js
const link = document.querySelector('a');

link.addEventListener('click', function(event){
  event.preventDefault(); // 기본 이동 차단
  console.log('링크 클릭 기본 동작이 막혔습니다.');
});
</code></pre><br />

<hr />
<h2 id="참고자료">참고자료</h2>
<p>코드잇 | 자바스크립트 이벤트</p>