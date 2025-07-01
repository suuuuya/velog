<p>자바스크립트 내장 객체 <code>Math</code> 객체의 다양한 메소드 정리
<br /><br /></p>
<h2 id="✅-절댓값-absolute-value">✅ 절댓값 (Absolute Value)</h2>
<p><code>abs</code> : absolute의 약자.</p>
<pre><code class="language-js">console.log(Math.abs(-10)); // 10
console.log(Math.abs(10)); // 10</code></pre>
<br />

<h2 id="✅-최댓값-maximum">✅ 최댓값 (Maximum)</h2>
<p>가지고 있는 값들 중 가장 큰 값 리턴</p>
<pre><code class="language-js">console.log(Math.max(2, -1, 4, 5, 0)); // 5</code></pre>
<br />

<h2 id="✅-최솟값-minimum">✅ 최솟값 (Minimum)</h2>
<p>가지고 있는 값들 중 가장 작은 값 리턴</p>
<pre><code class="language-js">console.log(Math.min(2, -1, 4, 5, 0)); // -1</code></pre>
<br />

<h2 id="✅-거듭제곱-exponentiation">✅ 거듭제곱 (Exponentiation)</h2>
<p><code>Math.pow(x, y)</code>를 하면 <code>x</code>의 <code>y</code>승의 결괏값이 리턴</p>
<pre><code class="language-js">console.log(Math.pow(2, 3)); // 8
console.log(Math.pow(5, 2)); // 25</code></pre>
<br />

<h2 id="✅-제곱근-square-root">✅ 제곱근 (Square Root)</h2>
<p>제곱의 반대. <code>Math.sqrt(x)</code>를 하면 <code>x</code>의 제곱근 리턴
음수가 담겼다면 <code>NaN</code>을 반환한다.</p>
<pre><code class="language-js">console.log(Math.sqrt(25)); // 5
console.log(Math.sqrt(49));// 7
console.log(Math.sqrt(-1)); //NaN</code></pre>
<br />

<h2 id="✅-반올림-round">✅ 반올림 (Round)</h2>
<p><code>Math.round(x)</code>를 하면 <code>x</code>의 반올림된 값이 리턴</p>
<pre><code class="language-js">console.log(Math.round(2.3)); // 2
console.log(Math.round(2.4)); // 2
console.log(Math.round(2.49)); // 2
console.log(Math.round(2.5)); // 3
console.log(Math.round(2.6)); // 3</code></pre>
<br />

<h2 id="✅-버림과-올림-floor-and-ceil">✅ 버림과 올림 (Floor and Ceil)</h2>
<p>소수 부분이 얼마인지와는 상관없이 리턴된다.</p>
<pre><code class="language-js">// floor
console.log(Math.floor(2.4)); // 2
console.log(Math.floor(2.49)); // 2
console.log(Math.floor(2.8)); // 2
// ceil
console.log(Math.ceil(2.4)); // 3
console.log(Math.ceil(2.49)); // 3
console.log(Math.ceil(2.8)); // 3</code></pre>
<br />

<h2 id="✅-난수-random">✅ 난수 (Random)</h2>
<p><code>Math.random</code>을 하면 0 이상 1 미만의 값이 랜덤으로 리턴된다.</p>
<pre><code class="language-js">console.log(Math.random()); // 0.21458369059793236
console.log(Math.random()); // 0.6622040803059857
...</code></pre>
<br />

<p>이 외, 더 많은 메소드는 <a href="https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Math">Math | MDN</a> 참고!</p>