<h2 id="✅-변수variable">✅ 변수(Variable)</h2>
<p>자바스크립트에서 사용되는 변수 선언 방식에는 3가지가 있다.
<code>var</code>, <code>let</code>, <code>const</code> 셋의 차이점은...</p>
<ul>
<li>중복 선언과 재할당</li>
<li>스코프 범위</li>
<li>호이스팅
🌠 <strong>호이스팅(hoisting)이란?</strong> 스코프 내부 어디서든 변수 선언은 최상위에 선언된 것처럼 행동한다는 의미. 쉽게 말해 **선언이 코드 맨 위로 끌어올려지는 것</li>
<li>*<br />

</li>
</ul>
<h3 id="var">var</h3>
<p><code>var</code>에서는 <strong>중복 선언과 재할당이 모두 가능</strong>하다.
마지막에 할당된 값이 최종 변수 값으로 저장.</p>
<h4 id="📄-var-스코프-범위">📄 var 스코프 범위</h4>
<p><code>var</code>는 <strong>함수 단위 스코프</strong>.
<code>var</code> 변수가 선언된 함수 내부의 어디서든 참조가 가능하지만, 외부 참조는 불가능하다.</p>
<h4 id="📄-var-호이스팅">📄 var 호이스팅</h4>
<p>호이스팅이 발생한다.</p>
<p>e.g.</p>
<pre><code class="language-js">console.log(a); // undefined
var a = 10;
console.log(a); // 10</code></pre>
<p>JS 실행 전.
선언만 위로 올라가고 할당은 원래 위치에 남아있기 때문에 처음 출력은 <code>undefined</code></p>
<pre><code class="language-js">var a;           // 선언이 호이스팅 됨
console.log(a);  // undefined (초기값은 undefined)
a = 10;         // 값 할당
console.log(a); // 10</code></pre>
<p><br /><br /></p>
<h3 id="let">let</h3>
<p>변할 수 있는 값.
<code>let</code>은 중복 선언을 허용하지 않는다. 대신 재할당은 <code>var</code>와 동일하게 가능하다.</p>
<pre><code class="language-js">let a = 5;
let a = 10; // SyntaxError
// ----------------------- 
let a = 5;
console.log(a); // 5
a = 10;
console.log(a); // 10</code></pre>
<h4 id="📄-let-스코프-범위">📄 let 스코프 범위</h4>
<p><code>let</code>은 <strong>블록 단위 스코프</strong>
<code>{}</code> 블록 내부에 선언된 <code>let</code>은 외부에서 참조되지 않는다.</p>
<h4 id="📄-let-호이스팅">📄 let 호이스팅</h4>
<p><code>let</code>도 선언은 호이스팅 되지만, <code>var</code>와는 다르게 초기화 단계 전에는 사용할 수 없어, 뒤에서 선언된 변수를 앞에 참조하려니 에러가 발생한다.</p>
<pre><code class="language-js">console.log(b); // ReferenceError
let b = 20;
console.log(b);</code></pre>
<pre><code class="language-js">let b;          // 선언은 호이스팅되지만 TDZ 때문에 초기화되는 시점 전까지 접근 불가
console.log(b); // 여기서 ReferenceError
b = 20;
console.log(b);</code></pre>
<p>🌠** TDZ(Temporal Dead Zone)란? **
일시적 사각지대라는 뜻. 선언된 변수가 선언 전에 접근 불가능한 구간
<br /><br /></p>
<h3 id="const">const</h3>
<p>변하지 않는 값(상수).
<code>const</code>에서도 <code>let</code>과 동일하게 중복 선언을 허용하지 않는다.
 상수를 선언하는 키워드이기 때문에 다른 변수들과 달리 재할당도 불가능하다.</p>
<pre><code class="language-js">const PI = 3.14; </code></pre>
<p>🌠 변수명을 반드시 대문자로 써야하는 규칙은 없지만,
협업과 가독성, 유지보수 측면을 생각하면 주로 대문자로 선언하는게 좋을 듯하다.</p>
<h4 id="📄-const-스코프-범위">📄 const 스코프 범위</h4>
<p><code>const</code>은 <strong>블록 단위 스코프</strong>
<code>{}</code> 블록 내부에 선언된 <code>let</code>은 외부에서 참조되지 않는다.</p>
<h4 id="📄-const-호이스팅">📄 const 호이스팅</h4>
<p><code>let</code>과 동일하다.</p>
<br />

<p><strong>📊 표 정리</strong></p>
<table>
<thead>
<tr>
<th></th>
<th>var</th>
<th>let</th>
<th>const</th>
</tr>
</thead>
<tbody><tr>
<td>용도</td>
<td>과거 코드, 함수 내 변수 선언</td>
<td>값이 변경될 변수 선언</td>
<td>상수 선언, 불변 참조 선언</td>
</tr>
<tr>
<td>재선언</td>
<td>가능</td>
<td>불가능<br />(같은 스코프 내)</td>
<td>불가능<br />(같은 스코프 내)</td>
</tr>
<tr>
<td>재할당</td>
<td>가능</td>
<td>가능</td>
<td>불가능 <br />(객체 프로퍼티는 변경 가능)</td>
</tr>
<tr>
<td>스코프</td>
<td>함수 스코프</td>
<td>블록 스코프</td>
<td>블록 스코프</td>
</tr>
<tr>
<td>호이스팅</td>
<td>선언 및 초기화 hoisting됨</td>
<td>선언 hoisting만 됨</td>
<td>선언 hoisting만 됨</td>
</tr>
</tbody></table>
<p><br /><br /><br /></p>
<h2 id="✅-함수function">✅ 함수(function)</h2>
<p>함수를 사용하는 이유는 코드를 재사용할수 있다는 점.
<br /></p>
<h3 id="기본-함수-구문">기본 함수 구문</h3>
<pre><code class="language-js">function name (parameter1, parameter2,...) {
    ...
}</code></pre>
<p>함수가 받을 매개변수를 지정해 줄 수 있다.</p>
<pre><code class="language-js">function drink (cup) { // cup은 매개변수(parameter)
    ...
}
drink(&quot;커피&quot;); // 커피는 인자(argument): 실제로 전달하는 값 </code></pre>
<br />

<h3 id="함수-선언식">함수 선언식</h3>
<pre><code class="language-js">function hello() {
  console.log(&quot;Hello!&quot;);
}
hello(); // &quot;Hello!&quot;</code></pre>
<br />

<h3 id="함수-표현식">함수 표현식</h3>
<p>함수 표현식이란, 변수를 선언하고 함수를 대입하는 방식</p>
<pre><code class="language-js">const bye = function() {
  console.log(&quot;Bye!&quot;);
}
bye(); // &quot;Bye!&quot;</code></pre>
<h4 id="🌠-함수-선언문-vs-함수-표현식-차이">🌠 <strong>함수 선언문 VS 함수 표현식 차이</strong></h4>
<p>함수 선언식과 표현식은 호이스팅의 차이가 있다.</p>
<ul>
<li><strong>함수 선언문</strong>: 호이스팅 시, 함수 전체가 끌어올려짐 → 선언 전에 호출 가능(전역, 재사용)</li>
<li><strong>함수 표현식</strong>: 변수 선언만 호이스팅 됨 → 선언 전 호출 불가(콜백, 조건부)
<br /><br /></li>
</ul>
<h3 id="함수-선언">함수 선언</h3>
<pre><code class="language-js">function add (x, y) {
  var result = x + y;
  console.log(result);
  return result;
}</code></pre>
<br />

<h3 id="함수-호출">함수 호출</h3>
<pre><code class="language-js">add(3, 5);</code></pre>
<br />

<h3 id="참고-함수-이름-지정">(참고) 함수 이름 지정</h3>
<p>아래와 같이 함수의 기능을 설명하는 네이밍 규칙을 만들면 좋을 것 같아서 가져왔다.</p>
<p>show.. : 무언가를 보여준다.
get.. : 값을 반환한다.
calc.. : 무언가를 계산한다.
create.. : 무언가를 만든다.
check.. : 무언가를 확인하고 불리언 등을 반환한다.</p>
<pre><code class="language-js">showMessage(..)        // shows a message
getAge(..)             // returns the age (gets it somehow)        
calcSum(..)            // calculates a sum and returns the result
createForm(..)         // creates a form (and usually returns it)
checkPermission(..)    // checks a permission, returns true/false</code></pre>
<p><br /><br /></p>
<hr />
<h2 id="참고자료">참고자료</h2>
<p>코드잇 토픽
<a href="https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/var">var | MDN</a>
<a href="https://www.w3schools.com/js/js_functions.asp">Function | W3Schools</a>
<a href="https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Functions">Function | MDN</a></p>