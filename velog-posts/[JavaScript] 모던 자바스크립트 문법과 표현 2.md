<h2 id="✅-옵셔널-체이닝">✅ 옵셔널 체이닝</h2>
<blockquote>
<p>중첩된 객체의 프로퍼티나 메소드를 안전하게 접근할 수 있는 문법</p>
</blockquote>
<p>✔️ <code>?.</code> 연산자를 사용한다.
✔️ undefined 또는 null 값이 중간에 있어도 에러 없이 undefined를 반환한다.</p>
<br />

<p>*<em>🌠 중첩 객체를 다룰 때 한가지 조심해야 될 부분이 있다. *</em></p>
<p>여러 가지 상황에 맞춰 데이터를 다루다 보면 때로는 우리가 예상한 프로퍼티를 가지고 있지 않을 수도 있는데,</p>
<p>if문을 활용할 수도 있지만, 일반적으로는 간결하게 AND 연산자를 활용해서 이 문제를 해결하곤 했었다.</p>
<pre><code class="language-js">if(user &amp;&amp; user.address &amp;&amp; user.address.city){
  console.log(user.address.city);
}</code></pre>
<p>그런데 이마저도 객체의 이름이나 프로퍼티의 이름이 길어질수록 가독성이 나빠지는 문제가 있다.
<br /><br /></p>
<p>✔️ 이런 상황에 훨씬 더 코드를 간결하게 사용할 수 있는 문법이 바로 <strong>옵셔널 체이닝(Optional Chaining)</strong> 이다.</p>
<p>e.g.)</p>
<pre><code class="language-js">const user = {};

// ❌ 오류: Cannot read property 'city' of undefined
console.log(user.address.city); 


// ✅ undefined
// ✔️ user.address가 존재하면 city 반환,
// ✔️ 없으면 undefined 반환,
// ✔️ 에러 없이 코드가 실행됨.
console.log(user.address?.city); 


// 응용 버전
function printCatName(user) {
  console.log(user.cat?.name ?? '함께 지내는 고양이가 없습니다.');
}
const user2 = {
  name: 'Young',
}
printCatName(user2); // 함께 지내는 고양이가 없습니다.</code></pre>
<p><br /><br /></p>
<h2 id="✅-구조-분해-destructuring">✅ 구조 분해 Destructuring</h2>
<blockquote>
<p>배열이나 객체의 값을 쉽게 꺼내어 변수에 할당하는(꺼내 쓰기 쉽게 분해하는) 문법</p>
</blockquote>
<p>배열과 객체와 같이 내부에 여러 값을 담고 있는 데이터 타입을 다룰 때 Destructuring 문법을 활용하면, 배열의 요소나 객체의 프로퍼티 값들을 개별적인 변수에 따로 따로 할당해서 다룰 수 있다.</p>
<p>✔️ ES6(2015)에서 도입된 모던 자바스크립트 기능
✔️ 코드의 가독성과 간결성을 높여준다.
<br /></p>
<pre><code class="language-js">// Array Destructuring
const members = ['코딩하는효준', '글쓰는유나', '편집하는민환'];
const [macbook, ipad, coupon] = members;

console.log(macbook); // 코딩하는효준
console.log(ipad); // 글쓰는유나
console.log(coupon); // 편집하는민환

// Object Destructuring
const macbookPro = {
  title: '맥북 프로 16형',
  price: 3690000,
};

const { title, price } = macbookPro;

console.log(title); // 맥북 프로 16형
console.log(price); // 3690000
</code></pre>
<p>🌠 <strong>주의 사항</strong></p>
<ol>
<li>배열 구조 분해 ➔ 순서 중요</li>
<li>객체 구조 분해 ➔ 변수명 = 프로퍼티명
(변수명을 바꾸고 싶으면 : 사용)<br />

</li>
</ol>
<h4 id="rest-문법-활용">rest 문법 활용</h4>
<pre><code class="language-js">// Array Destructuring
const members = ['코딩하는효준', '글쓰는유나', undefined, '편집하는민환', '촬영하는재하'];
const [macbook, ipad, airpod = '녹음하는규식', ...coupon] = members;

console.log(macbook); // 코딩하는효준
console.log(ipad); // 글쓰는유나
console.log(airpod); // 녹음하는규식
console.log(coupon); // (2) [&quot;편집하는민환&quot;, &quot;촬영하는재하&quot;]

// Object Destructuring
const macbookPro = {
  title: '맥북 프로 16형',
  price: 3690000,
  memory: '16 GB 2667 MHz DDR4',
  storage: '1TB SSD 저장 장치',
};

const { title, price, color = 'silver', ...rest } = macbookPro;

console.log(title); // 맥북 프로 16형
console.log(price); // 3690000
console.log(color); // silver
console.log(rest); // {memory: &quot;16 GB 2667 MHz DDR4&quot;, storage: &quot;1TB SSD 저장 장치&quot;}
</code></pre>
<br />

<h2 id="✅-에러와-에러-객체">✅ 에러와 에러 객체</h2>
<p>자바스크립트에서 에러가 발생하면 그 순간 프로그램 자체가 멈춰버리고 이후의 코드가 동작하지 않는다.</p>
<p>에러가 발생하면 에러에 대한 정보를 name과 message라는 프로퍼티로 담고 있는 에러 객체가 만들어 지는데, 
<br />
대표적인 에러 객체는 . .</p>
<p>✔️ SyntaxError
✔️ ReferenceError
✔️ TypeError</p>
<br />

<p><strong>🌠 에러 객체를 직접 만들 수도 있다.</strong>
new 키워드와 에러 객체 이름을 딴 함수를 통해 에러 객체를 만들 수 있고,
throw 키워드로 에러를 발생시킬 수 있습니다.</p>
<pre><code class="language-js">throw new TypeError('타입 에러가 발생했습니다.');
</code></pre>
<p><br /><br /></p>
<h2 id="✅-trycatch문">✅ try...catch문</h2>
<blockquote>
<p>자바스크립트에서 대표적인 에러 처리 방법</p>
</blockquote>
<pre><code class="language-js">try {
  // 실행할 코드
} catch (error) {
  // 에러 발생 시 동작할 코드
}</code></pre>
<p><code>try</code>문 안에서 실행할 코드를 작성하고,
try문에서 에러가 발생한 경우에 실행할 코드를 <code>catch</code> 문 안에 작성</p>
<p>try문에서 발생한 에러 객체가 catch문의 첫 번째 파라미터로 전달된다. 
try문에서 에러가 발생하지 않을 경우 catch문의 코드는 동작하지 않는다.</p>
<h4 id="finally문">finally문</h4>
<p>try...catch문에서 에러의 유무와 상관없이 항상 동작해야할 코드가 필요하다면 finally문을 활용할 수 있다.</p>
<pre><code class="language-js">try {
  // 실행할 코드
} catch (error) {
  // 에러가 발상했을 때 실행할 코드
} finally {
  // 항상 실행할 코드
}
</code></pre>
<br />

<hr />
<h2 id="참고자료">참고자료</h2>
<p>코드잇 | 모던 자바스크립트</p>