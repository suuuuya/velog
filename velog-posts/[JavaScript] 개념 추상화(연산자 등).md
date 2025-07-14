<h2 id="✅-복합-할당-연산자">✅ 복합 할당 연산자</h2>
<p>가독성, 코드량 감소, 유지보수 용이</p>
<pre><code class="language-js">x = x + 2; // x에 2을 더해서 다시 x에 할당
x += 2;    // 복합 할당 연산자 - 위와 같은 의미

// 예제
let x = 10;
x += 5;  // 15
x -= 2;  // 13
x *= 3;  // 39</code></pre>
<p>위와 같이 <code>+=</code>, <code>-=</code>, <code>*=</code>, <code>/=</code>, <code>%=</code> 등의 복합 할당 연산자를 사용하면, 더 간결한 표현으로 연산을 처리할 수 있다.
<br /><br /></p>
<h2 id="✅-증가-감소-연산자">✅ 증가 감소 연산자</h2>
<p>값을 1씩 증가시키거나 감소시킬 때</p>
<pre><code class="language-js">let score = 10;

score++;  // score의 값을 1 증가시킴 (score = score + 1과 같은 의미)
score--;  // score의 값을 1 감소시킴 (score = score - 1과 같은 의미)</code></pre>
<p><br /><br /></p>
<h2 id="✅-null-병합-연산자-">✅ null 병합 연산자 ??</h2>
<p>물음표 두 개(??)를 사용해서 null 혹은 undefined 값을 가려내는 연산자</p>
<pre><code class="language-js">const example1 = null ?? 'I'; // I
const example2 = undefined ?? 'love'; // love
const example3 = 'Codeit' ?? 'JavaScript'; // Codeit

console.log(example1, example2, example3); // I love Codeit</code></pre>
<p><br /><br /></p>
<h2 id="✅-or-연산자와-비교">✅ OR 연산자(||)와 비교</h2>
<p>OR 연산자 (||)와 동작하는 방식이 비슷해 보인다.
null 병합 연산자(??)는 왼편의 값이 null이나 undefined인지 확인하고 OR 연산자(||)는 왼편의 값이 falsy인지를 확인하기 때문에 아래 코드와 같이 null이나 undefined가 아닌 falsy 값을 활용할 때 결과가 서로 다르다.</p>
<pre><code class="language-js">const title1 = false || 'codeit';
const title2 = false ?? 'codeit';

console.log(title1); // codeit
console.log(title2); // false

const width1 = 0 || 150;
const width2 = 0 ?? 150;

console.log(width1); // 150
console.log(width2); // 0
</code></pre>
<p><br /><br /></p>
<h2 id="✅-연산자-우선순위">✅ 연산자 우선순위</h2>
<p><a href="https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Operator_precedence">연산자 우선순위 - JavaScript | MDN</a></p>
<h3 id="and-와-or-연산자의-연산-우선순위">AND 와 OR 연산자의 연산 우선순위</h3>
<p>AND 연산자나 OR 연산자 중 하나만 계속해서 사용할 때는 문제 없지만, 만약 AND 연산자와 OR 연산자를 섞어서 사용할 때는 연산의 우선순위가 존재한다.</p>
<p><strong>🌠 AND 와 OR 연산자 사이에서는 AND 연산자의 우선순위가 더 높다.</strong></p>
<pre><code class="language-js">console.log(true || false &amp;&amp; false); // true
console.log((true || false) &amp;&amp; false); // false

console.log('Codeit' || NaN &amp;&amp; false); // Codeit
console.log(('Codeit' || NaN) &amp;&amp; false); // false</code></pre>
<p>자바스크립트에서 AND와 OR연산자는 무조건 불린 값을 리턴하는게 아니라, 왼쪽 피연산자 값의 유형에 따라서 두 피연산자 중 하나를 리턴하는 방식으로 동작한다.</p>
<p>*<em>AND 연산자는 *</em>
✔️ 왼쪽 피연산자가 falsy값일 때 왼쪽 피연산자를 리턴
✔️ 왼쪽 피연산자가 truthy값일 때 오른쪽 피연산자를 리턴</p>
<p>*<em>OR 연산자는 *</em>
✔️ 왼쪽 피연산자가 falsy 일 때 오른쪽 피연산자를 리턴
✔️ 왼쪽 피연산자가 truthy 일 때 왼쪽 피연산자를 리턴</p>
<pre><code class="language-js">console.log(null &amp;&amp; undefined); // null
console.log(0 || true); // true
console.log('0' &amp;&amp; NaN); // NaN
console.log({} || 123); // {}</code></pre>
<p><br /><br /></p>
<h2 id="✅-조건부-연산자">✅ 조건부 연산자</h2>
<blockquote>
<p>삼항 연산자 (Ternary operator)라고도 불리는 이 연산자는 자바스크립트에서 세 개의 피연산자를 가지는 유일한 연산자다.</p>
</blockquote>
<p>✔️ if문과 같은 원리로 조건에 따라 값을 결정할 때 활용</p>
<pre><code class="language-js">const cutOff = 80;

const passChecker = (score) =&gt; score &gt; cutOff ? '합격입니다!' : '불합격입니다!';

console.log(passChecker(75));</code></pre>
<p>🌠 간단한 조건식의 경우에는 <strong>if문 보다 훨씬 더 간결하게 표현할 수 있는 장점</strong>이 있지만 <u>내부에 변수나 함수를 선언한다거나 반복문 같은 표현식이 아닌 문장은 작성할 수 없다는 한계</u>가 있기 때문에 if문을 완벽하게 대체할 수는 없다는 점
<br /><br /></p>
<h2 id="✅-return-vs-consolelog">✅ return VS console.log()</h2>
<ul>
<li>return 문은 값을 호출한 자리에 반환</li>
<li>console.log() 는 주어진 인수를 출력<br />

</li>
</ul>
<h3 id="return문">return문</h3>
<p>return을 만나면 함수 실행이 즉시 종료됨
함수 밖으로 값을 내보내기 위해 사용.</p>
<p><strong>1. 함수 실행 중단</strong>
num이 음수이면, return; 만 실행되어 함수가 바로 실행 종료</p>
<pre><code class="language-js">function checkNumber(num) {
  if (num &lt; 0) {
    console.log(&quot;음수는 처리하지 않습니다.&quot;);
    return; // 여기서 함수 실행 종료
  }

  console.log(&quot;입력한 수의 제곱은:&quot;, num * num);
}

checkNumber(-5); // &quot;음수는 처리하지 않습니다.&quot;
checkNumber(3);  // &quot;입력한 수의 제곱은: 9&quot;</code></pre>
<p><strong>2. 코드 무시</strong></p>
<pre><code class="language-js">function sayHi() {
  console.log(&quot;안녕하세요!&quot;);
  return;
  console.log(&quot;이 코드는 실행될까요?&quot;);
}

sayHi(); // 안녕하세요!</code></pre>
<p><br /><br /></p>
<h2 id="✅-옵셔널-파라미터">✅ 옵셔널 파라미터</h2>
<p>함수의 파라미터 중에서 선택적으로 값을 전달받을 수 있는 파라미터.
 함수 호출 시 해당 파라미터에 값을 전달하지 않아도 오류가 발생하지 않는다.</p>
<p> 옵셔널 파라미터 특징: 선택적 입력, 기본값 설정, 유연성</p>
<pre><code class="language-js">function greet(name, greeting = &quot;Hello&quot;) {
  console.log(`${greeting}, ${name}!`);
}

greet(&quot;Alice&quot;); // 출력: Hello, Alice!
greet(&quot;Bob&quot;, &quot;Hi&quot;); // 출력: Hi, Bob!</code></pre>
<br />



<hr />
<p>코드잇 프로그래밍 핵심 개념 | 추상화 토픽</p>