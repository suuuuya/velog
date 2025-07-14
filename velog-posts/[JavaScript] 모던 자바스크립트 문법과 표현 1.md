<p>프로그래밍 언어도 기존의 문제점을 보완하거나 유용한 기능을 추가해서 새로운 버전을 만들기도 하는데, 최근에 가장 많이 쓰이는 형태의 자바스크립트를 <strong>모던 자바스크립트</strong>라고 한다.</p>
<h2 id="✅-모던-자바스크립트">✅ 모던 자바스크립트</h2>
<blockquote>
<p><strong>E</strong>CMA<strong>S</strong>cript 2015(ES6) 이후에 도입된 최신 문법과 기능을 통칭</p>
</blockquote>
<p>ECMAScript는 JavaScript가 갖추어야 할 내용을 정리해둔 <code><strong>설명서</strong></code>라고 이해하면 쉽다.</p>
<p>🌠 ECMA란? 정보통신과 프로그래밍 언어의 표준을 제정하는 국제 표준화 기구
🌠 ECMAScript란? 프로그래밍 언어의 표준</p>
<p><a href="https://www.ecma-international.org/publications/standards/Ecma-262.htm">ECMAScript의 공식 문서</a></p>
<p><br /><br /></p>
<h2 id="✅-자바스크립트-문장과-표현식">✅ 자바스크립트 문장과 표현식</h2>
<p>문장과 표현식에 대한 개념</p>
<h3 id="문장-statements">문장 (statements)</h3>
<blockquote>
<p>우리가 작성하는 모든 자바스크립트 코드는 모두 문장과 표현식으로 구성되어 있다.</p>
</blockquote>
<p>*<em>🌠 자바스크립트에서 문장은? *</em>
어떤 동작이 일어나도록 작성된 최소한의 코드 덩어리를 가리킨다.</p>
<pre><code class="language-js">// x라는 변수를 선언하는 동작이 일어나는 하나의 문장이고,
let x; 
// x에 3이라는 값을 할당하는 동작이 일어나는 하나의 문장
x = 3;
// 문장
if (x &lt; 5) {
  console.log('x는 5보다 작다');
} else {
  console.log('x는 5와 같거나 크다');
}
// 반복 동작을 하는 문장의 예시
for (let i = 0; i &lt; 5; i++) {
  console.log(i);
}</code></pre>
<p>선언문, 할당문, 조건문, 반복문 .. 이렇게 끝에 문이라고 붙은 이유가 모두 동작을 수행하는 문장이기 때문이다.
<br /><br /></p>
<h3 id="표현식-expressions">표현식 (expressions)</h3>
<blockquote>
<p>표현식은 결과적으로 하나의 값이 되는 모든 코드를 가리킨다.</p>
</blockquote>
<pre><code class="language-js">// 어떤 하나의 값을 그대로 작성하는 것도 표현식이지만,
5 // 5

'string' // string

//연산자를 이용한 연산식도 결국은 하나의 값이 되고,
5 + 7 // 12

'I' + ' Love ' + 'Codeit' // I Love Codeit

// 마지막 네 줄처럼 선언된 변수를 호출하거나, 
// 객체의 프로퍼티에 접근하는 것도 결국에는 하나의 값으로 평가된다.
true &amp;&amp; null // null
const title = 'JavaScript';
const codeit = {
  name: 'Codeit'
};
const numbers = [1, 2, 3];

typeof codeit // object
title // JavaScript
codeit.name // Codeit
numbers[3] // undefined</code></pre>
<p>길이와는 상관없이 결과적으로 하나의 값이 되는 코드를 모두 표현식
<br /><br /></p>
<h3 id="표현식이면서-문장-문장이면서-표현식">표현식이면서 문장, 문장이면서 표현식</h3>
<p>표현식은 보통 문장의 일부로 쓰이지만, 그 자체로 문장일 수도 있다.</p>
<p><strong>가장 대표적인 예시가 할당식과 함수 호출</strong></p>
<pre><code class="language-js">// 할당 연산자는 값을 할당하는 동작도 하지만, 할당한 값을 그대로 가지는 표현식이다.
title = 'JavaScript'; // JavaScript

// 함수 호출은 함수를 실행하는 동작도 하지만, 실행한 함수의 리턴 값을 가지는 표현식이다.
sayHi(); // sayHi 함수의 리턴 값

// console.log 메소드는 콘솔에 아규먼트를 출력하는 동작도 하지만, undefined 값을 가지는 표현식이다.
console.log('hi'); // undefined</code></pre>
<p><br /><br /></p>
<h3 id="표현식인-문장-vs-표현식이-아닌-문장">표현식인 문장 vs 표현식이 아닌 문장</h3>
<p>문장은 다시 표현식인 문장과, 표현식이 아닌 문장으로 나눌 수 있다.
구분하는 가장 간단한 방법은 우리가 구분하고자 하는 문장을 변수에 할당하거나, 어떤 함수의 아규먼트로 전달해보는 것
<br /><br /></p>
<h2 id="✅-다양한-객체의-프로퍼티-표기법">✅ 다양한 객체의 프로퍼티 표기법</h2>
<p>ES2015 이후부터는 자바스크립트에서 변수나 함수를 활용해서 프로퍼티를 만들 때 프로퍼티 네임과 변수나 함수 이름이 같다면 다음과 같이 축약해서 사용할 수 있다.</p>
<pre><code class="language-js">function sayHi() {
  console.log('Hi!');
}

const title = 'codeit';
const birth = 2017;
const job = '프로그래밍 강사';

const user = {
  title, 
  birth, 
  job, 
  sayHi,
};

console.log(user); // {title: &quot;codeit&quot;, birth: 2017, job: &quot;프로그래밍 강사&quot;, sayHi: ƒ}



// ✔️ 메소드를 작성할 때도 다음과 같이 function 키워드를 생략할 수가 있다.

const user = {
  firstName: 'Tess',
  lastName: 'Jang',
  getFullName() {
    return `${this.firstName} ${this.lastName}`;
  },
};

console.log(user.getFullName()); // Tess Jang


// ✔️ 대괄호를 활용 예시
const propertyName = 'birth';
const getJob = () =&gt; 'job';

const codeit = {
  ['topic' + 'name']: 'Modern JavaScript',
  [propertyName]: 2017,
  [getJob()]: '프로그래밍 강사',
};

console.log(codeit);
</code></pre>
<br />

<h3 id="기본-프로퍼티-표기법">기본 프로퍼티 표기법</h3>
<p>자바스크립트에서 객체의 프로퍼티를 접근하거나 설정할 때 사용하는 2가지 표기법.</p>
<h4 id="점-표기법">점 표기법</h4>
<p>가장 일반적이고 가독성이 좋음</p>
<pre><code class="language-js">obj.key

const user = { name: '이름', age: 26 };
console.log(user.name); // '이름'</code></pre>
<h4 id="대괄호-표기법">대괄호 표기법</h4>
<p>프로퍼티 이름이 문자열 형태로 들어감
공백, 특수문자, 변수 사용 가능.</p>
<pre><code class="language-js">obj['key']

console.log(user['age']); // 26
const prop = 'name';
console.log(user[prop]); // 이름</code></pre>
<br />

<h3 id="동적-프로퍼티">동적 프로퍼티</h3>
<p>ES6에서 도입된 계산된 프로퍼티 이름</p>
<p>변수나 표현식을 [] 안에 넣어 프로퍼티 이름으로 사용</p>
<pre><code class="language-js">[key]: value

const key = 'score';
const obj = {
  [key]: 100
};
console.log(obj.score); // 100</code></pre>
<p><br /><br /></p>
<h3 id="중첩-객체-접근">중첩 객체 접근</h3>
<p>객체 안에 객체가 있을 때 점 표기법을 연속으로 사용.</p>
<pre><code class="language-js">obj.a.b

const user = {
  name: '이름',
  address: {
    city: 'Seoul',
    zip: '12345'
  }
};

console.log(user.address.city); // 'Seoul'</code></pre>
<p><br /><br /></p>
<h3 id="배열-프로퍼티">배열 프로퍼티</h3>
<p>객체의 프로퍼티 값으로 배열이 있을 경우, 배열 표기법과 점 표기법을 조합해 사용.</p>
<pre><code class="language-js">const obj = {
  list: [10, 20, 30]
};

console.log(obj.list[1]); // 20</code></pre>
<p><br /><br /></p>
<h3 id="함수-프로퍼티-메소드">함수 프로퍼티 (메소드)</h3>
<p>객체의 프로퍼티 값이 함수일 때는 메소드라고 부름.</p>
<pre><code class="language-js">obj.func()

const person = {
  name: '이름',
  greet: function(){
    console.log(`Hi, I'm ${this.name}`);
  }
};

person.greet(); // Hi, I'm 이름

// --------------------
// ES6 메소드 단축 표기법
const person = {
  greet(){
    console.log('Hello');
  }
};</code></pre>
<p><br /><br /></p>
<h2 id="✅-spread-구문">✅ Spread 구문</h2>
<blockquote>
<p>Iterable(반복 가능한 객체)의 값을 개별 요소로 펼치는 문법</p>
</blockquote>
<p>쉽게 말해 배열, 문자열, 객체 등 묶여있는 값을 하나하나 풀어서 다른 곳에 넣을 수 있다.</p>
<p>✔️ ... (점 세 개) 를 사용한다.</p>
<h4 id="사용-목적">사용 목적</h4>
<ul>
<li>배열 복사</li>
<li>배열 합치기</li>
<li>함수의 인자로 전달</li>
<li>객체 복사 및 병합
<br /><br /></li>
</ul>
<h3 id="🌠-객체-spread하기">🌠 객체 Spread하기</h3>
<p>중괄호 안에서 객체를 spread 하게되면, 해당 객체의 프로퍼티들이 펼쳐지면서 객체를 복사할 수가 있다.</p>
<pre><code class="language-js">const codeit = { 
  name: 'codeit', 
};

const codeitClone = { 
  ...codeit, // spread 문법!
};

console.log(codeit); // {name: &quot;codeit&quot;}
console.log(codeitClone); // {name: &quot;codeit&quot;}
</code></pre>
<p> 다른 객체가 가진 프로퍼티에 다른 프로퍼티를 추가해서 새로운 객체를 만들 때 활용할 수도 있다.</p>
<pre><code class="language-js">const latte = {
  esspresso: '30ml',
  milk: '150ml'
};

const cafeMocha = {
  ...latte,
  chocolate: '20ml',
}

console.log(latte); // {esspresso: &quot;30ml&quot;, milk: &quot;150ml&quot;}
console.log(cafeMocha); // {esspresso: &quot;30ml&quot;, milk: &quot;150ml&quot;, chocolate: &quot;20ml&quot;}


// --------------------------

const webPublishing = ['HTML', 'CSS'];
const interactiveWeb = [...webPublishing, 'JavaScript'];

console.log(webPublishing);
console.log(interactiveWeb);

const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];

const arr3 = [...arr1, ...arr2];
console.log(arr3);


// --------------------------
// 배열은 객체로 펼칠 수 있지만 객체는 배열로 펼칠 수 없다는 점

const members = ['태호', '종훈', '우재'];
const newObject = { ...members };

console.log(newObject); // {0: &quot;태호&quot;, 1: &quot;종훈&quot;, 2: &quot;우재&quot;}

const topic = {
  name: '모던 자바스크립트',
  language: 'JavaScript', 
}
const newArray = [...topic]; // TypeError!
</code></pre>
<p><strong>🌠 주의 사항</strong>
Spread 하면 새로운 배열을 만들거나 함수의 아규먼트로 쓸 수 있었지만,
객체로는 새로운 배열을 만들거나 함수의 아규먼트로 사용할 수는 없다.</p>
<p><strong>그렇기 때문에  객체를 spread할 때는 반드시 객체를 표현하는 중괄호 안에서 활용해야 한다는 점</strong></p>
<p><br /><br /></p>
<h2 id="✅-rest-구문">✅ Rest 구문</h2>
<blockquote>
<p>여러 값을 하나의 변수에 모아 담는 문법</p>
</blockquote>
<p>✔️ ... (점 세 개) 를 사용한다.
✔️ 나머지 값들을 배열로 묶음.
✔️ 배열, 객체 구조 분해, 함수 파라미터에서 자주 사용된다.</p>
<p>쉽게 말해, '나머지를 다 모아서 여기 담아줘' 라는 뜻</p>
<h4 id="사용-목적-1">사용 목적</h4>
<ul>
<li>함수의 가변 파라미터 처리</li>
<li>배열, 객체 구조 분해 시 나머지 요소 수집
<br /><br /></li>
</ul>
<h3 id="함수-파라미터에-사용">함수 파라미터에 사용</h3>
<p>...numbers 는 넘겨받은 모든 인자를 배열로 모은다.</p>
<pre><code class="language-js">function sum(...numbers){
  return numbers.reduce((a,b) =&gt; a+b, 0);
}

console.log(sum(1,2,3,4)); // 10</code></pre>
<br />

<h3 id="배열-구조-분해에서-사용">배열 구조 분해에서 사용</h3>
<p>rest 변수에 나머지 배열 요소가 담김.</p>
<pre><code class="language-js">const [a, ...rest] = [10, 20, 30, 40];
console.log(a);    // 10
console.log(rest); // [20, 30, 40]</code></pre>
<p><br /><br /></p>
<h2 id="✅-rest-vs-spread-차이">✅ Rest vs Spread 차이</h2>
<table>
<thead>
<tr>
<th>구분</th>
<th>문법</th>
<th>역할</th>
</tr>
</thead>
<tbody><tr>
<td><strong>Rest</strong></td>
<td>...변수<br />function fn(...args){}</td>
<td><strong>모은다 (collect)</strong><br />배열/객체의 나머지 요소를 하나로 묶음</td>
</tr>
<tr>
<td><strong>Spread</strong></td>
<td>...배열/객체<br />const arr2 = [...arr1];</td>
<td><strong>펼친다 (spread out)</strong><br />배열/객체의 요소를 개별로 풀어냄</td>
</tr>
</tbody></table>
<br />

<hr />
<h2 id="참고자료">참고자료</h2>
<p>코드잇 | 모던 자바스크립트</p>