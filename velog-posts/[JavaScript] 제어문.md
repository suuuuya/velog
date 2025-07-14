<h2 id="✅-제어문">✅ 제어문</h2>
<blockquote>
<p>주어진 조건에 따라 코드 블록을 실행하거나 반복실행 할 때 사용한다.</p>
</blockquote>
<br />

<h2 id="✅-조건문">✅ 조건문</h2>
<blockquote>
<p>주어진 조건식의 결과에 따라 코드블럭의 실행을 결정한다. </p>
</blockquote>
<p>조건식은 boolean(true, false)값으로 평가될 수 있는 표현식이다.</p>
<br />

<h3 id="📄ifelse문">📄if...else문</h3>
<p>조건식을 위에서부터 차례대로 검사, true인 블록만 실행</p>
<pre><code class="language-js">if (조건식 1) {
  // 조건식 1이 참이면 이 코드 블록이 실행
} else if (조건식 2) {
  //조건식 2가 참이면 이 코드 블록이 실행
} else {
  //조건식 1과 조건식 2가 모두 거짓이면 이 코드 블록이 실행
}</code></pre>
<br />

<h3 id="📄switch문">📄switch문</h3>
<p>변수 값과 case를 <code>===</code> (엄격 비교) 로 검사</p>
<p>🌠 <strong>주의할 점</strong>
<code>break</code> 없으면 아래 case까지 실행됨
case문의 마지막에는 반드시 break; 를 써줘야 된다.</p>
<pre><code class="language-js">switch (표현식) {
  case 표현식1:
    switch문의 표현식과 표현식1이 일치하면 실행될 문;
    break;
  case 표현식2:
    switch문의 표현식과 표현식2가 일치하면 실행될 문;
    break;
  default:
    switch문의 표현식과 일치하는 case문이 없을 때 실행될 문;
}</code></pre>
<br />

<h2 id="✅-반복문">✅ 반복문</h2>
<blockquote>
<p>코드를 반복 실행할 때 사용</p>
</blockquote>
<p>조건식의 평가가 거짓이 나올때 까지 반복하는 것
<br /></p>
<h3 id="📄for문">📄for문</h3>
<p>반복 횟수가 정해져 있을 때</p>
<pre><code class="language-js">for (변수 선언문 또는 할당문; 조건식; 증감식) {
  조건식이 참인 경우 반복 실행될 문;
}
for (let i = 0; i &lt; 5; i++) {
  console.log(i); // 0 1 2 3 4
}</code></pre>
<h4 id="중첩-for문">중첩 for문</h4>
<pre><code class="language-js">for (let i = 1; i &lt;= 6; i++) {
  for (let j = 1; j &lt;= 6; j++) {
    if (i + j === 6) console.log(`[${i}, ${j}]`);
  }
}
// 출력
[1, 5]
[2, 4]
[3, 3]
[4, 2]
[5, 1]</code></pre>
<br />

<h3 id="📄while문">📄while문</h3>
<p>조건식이 true인 동안 반복, 그리고 조건식의 결과가 거짓이면 실행을 종료한다.
조건을 만족하지 않으면 처음부터 실행 안됨</p>
<pre><code class="language-js">let i = 0;
while (i &lt; 5) {
  console.log(i);
  i++;
}</code></pre>
<br />

<h3 id="📄forin문">📄for...in문</h3>
<p>객체의 key를 반복</p>
<pre><code>const person = {name:'이름', age:25};

for (let key in person) {
  console.log(key, person[key]);
}
// name 이름
// age 25</code></pre><br />

<h3 id="📄forof문">📄for...of문</h3>
<p>배열, 문자열, NodeList 등 iterable 객체의 값(value) 반복</p>
<pre><code class="language-js">const arr = [10,20,30];

for (let value of arr) {
  console.log(value);
}
// 10 20 30</code></pre>
<br />


<h2 id="✅-제어-키워드">✅ 제어 키워드</h2>
<blockquote>
<p>반복문이나 switch 문 안에서 흐름을 제어할 때 사용</p>
</blockquote>
<br />

<h3 id="📄break">📄break</h3>
<p>반복문 또는 switch 문을 즉시 종료</p>
<pre><code class="language-js">for (let i = 0; i &lt; 10; i++) {
  if (i === 5) break;
  console.log(i); // 0 1 2 3 4
}</code></pre>
<h3 id="📄continue">📄continue</h3>
<p>이번 반복만 건너뛰고, 다음 반복으로 진행</p>
<pre><code class="language-js">for (let i = 0; i &lt; 5; i++) {
  if (i === 2) continue;
  console.log(i);// 0 1 3 4
}</code></pre>
<hr />
<h2 id="참고자료">참고자료</h2>
<p>코드잇 | 자바스크립트 프로그래밍 핵심 개념</p>