<h2 id="✅-자료형data-type이란">✅ 자료형(Data type)이란?</h2>
<blockquote>
<p>프로그래밍 언어로 조작 할 수 있는 값의 유형.</p>
</blockquote>
<p>자바스크립트에는 총 8개의 자료형이 존재한다.
<br /><br /></p>
<h2 id="✅-기본-자료형primitive-type">✅ 기본 자료형(Primitive Type)</h2>
<p>원시 타입은 값이 생성된 후에 그 값을 변경 할 수 없다.</p>
<h3 id="📄숫자형number">📄숫자형(Number)</h3>
<p>정수, 실수를 따로 구분하지 않고 모든 수를 실수 하나로 표현한다.</p>
<pre><code class="language-js">let num = 123;</code></pre>
<br />

<h3 id="📄문자열string">📄문자열(String)</h3>
<p>문자열을 표현할 때는 따옴표를 사용한다. <code>''</code>, <code>""</code>, <code>``</code></p>
<pre><code class="language-js">let str = 'apple'
let str2 = &quot;orange&quot;
let result = `과일 ${str}과${str2}`</code></pre>
<br />

<h3 id="📄불린형boolean">📄불린형(Boolean)</h3>
<p><code>true</code> , <code>false</code> 값으로만 나타내는 자료형
자바스크립트에서는 빈 문자열, 0, null, undefined, NaN 등의 값들은 <code>false</code>로 간주하게 된다.</p>
<pre><code class="language-js">console.log(2&gt;1); // true
console.log(2&lt;1); // false</code></pre>
<br />

<h3 id="📄undefined">📄Undefined</h3>
<p>값을 할당하지 않은 변수는 <code>undefined</code> 값을 가진다.
타입이 정해지지 않은 것. 즉, 변수 선언은 했지만 값을 할당하지 않은 상태</p>
<pre><code class="language-js">let name;
console.log(name); // undefined</code></pre>
<br />

<h3 id="📄null">📄Null</h3>
<p><code>null</code> 하나의 값만 가질 수 있다.
존재하지 않는 값, 비어있는 값, 알수 없는 값을 의미한다.
*&nbsp;의도적으로 값이 없음을 명시하기 위해 할당하는 값</p>
<pre><code class="language-js">let name = null;
console.log(name); // null
console.log(typeof name); // object</code></pre>
<br />

<h3 id="📄symbol">📄Symbol</h3>
<p>ES6 이후 새롭게 추가된 원시 타입
<code>Symbol</code>은 이름의 충돌 위험이 없는 고유한 값을 만들기 위해 사용하는 자료형.
객체의 숨겨진 속성 키 를 만들 때 사용한다.</p>
<pre><code class="language-js">const id1 = Symbol(&quot;id&quot;);
const id2 = Symbol(&quot;id&quot;);

console.log(id1 === id2); // false</code></pre>
<br />

<h3 id="📄bigint">📄BigInt</h3>
<p>아주 큰 정수를 표현하기 위한 자료형
<code>BigInt</code>를 쓰면 훨씬 큰 정수도 정확하게 표현할 수 있다.</p>
<pre><code class="language-js">// 뒤에 n을 붙이면 BigInt 자료형으로 인식
const bigNumber = 123456789012345678901234567890n;
console.log(bigNumber); // 123456789012345678901234567890n</code></pre>
<p><br /><br /></p>
<h2 id="✅-참조-자료형reference-types">✅ 참조 자료형(Reference Types)</h2>
<p>원시 타입을 제외한 거의 모든 것(객체, 배열, 함수 등)을 참조 타입으로 볼 수 있다.
참조 타입은 프로퍼티를 추가, 변경, 삭제가 가능하다는 특징이 있다.
기본 자료형: 값 자체를 저장
참조 자료형: 값이 있는 주소를 저장</p>
<h3 id="📄객체object">📄객체(Object)</h3>
<p>객체는 속성과 메소드를 가질 수 있다.</p>
<h4 id="객체-구문">객체 구문</h4>
<pre><code class="language-js">// e.g.
let user = new Object();
let user = {};
let user = {
    name : &quot;미지&quot;,
      age: 30,
      ...
}

let obj1 = { name: &quot;미지&quot; };
let obj2 = obj1;

obj2.name = &quot;호수&quot;;

console.log(obj1.name); // &quot;호수&quot;</code></pre>
<p><br /><br /></p>
<h2 id="🌠-typeof-연산자">🌠 typeof 연산자</h2>
<p>위의 자료형을 확인할 수 있는 연산자.
변수나 값 앞에 typeof를 붙이면 그 값의 타입을 문자열(String)로 알려준다.</p>
<pre><code class="language-js">console.log(typeof 123);       // &quot;number&quot;
console.log(typeof &quot;hello&quot;);   // &quot;string&quot;
console.log(typeof true);      // &quot;boolean&quot;
console.log(typeof undefined); // &quot;undefined&quot;
console.log(typeof null);      // &quot;object&quot;
console.log(typeof {});        // &quot;object&quot;
console.log(typeof []);        // &quot;object&quot;
console.log(typeof function(){}); // &quot;function&quot;</code></pre>
<p><a href="https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Operator_precedence">연산자 우선순위 | MDN</a>
<br /></p>
<h2 id="🌠-형-변환">🌠 형 변환</h2>
<h3 id="자동-형-변환">자동 형 변환</h3>
<ol>
<li>산술연산자
<code>+</code> 연산자는 숫자보다 문자열이 우선시 되기 때문에, 숫자형이 문자형을 만나면 문자형으로 변환하여 연산된다.<pre><code class="language-js">number + number // number
number + string // string
string + string // string
string + boolean // string
number + boolean // number
50 + 50; //100
100 + “점”; //”100점”
“100” + “점”; //”100점”
“10” + false; //”100&quot;
99 + true; //100
</code></pre>
</li>
</ol>
<p>//다른 연산자(-,*,/,%)
string * number // number
string * string // number
number * number // number
string * boolean //number
number * boolean //number
“2” * false; //0
2 * true; //2</p>
<pre><code>
2. 동치비교
```js
null == undefined // true 0 == 0
“0” == 0 // true 0 == 0
0 == false // true 0 == 0
“0” == false // true 0 == 0</code></pre><br />

<h3 id="명시적-형-변환">명시적 형 변환</h3>
<p>직접 자료형으로 바꾸는 경우</p>
<p>1.&nbsp;숫자로 변환</p>
<pre><code class="language-js">Number(&quot;123&quot;); // 123
Number(true); // 1
Number(false); // 0
Number(&quot;hello&quot;); // NaN
Number(“2”*2); //4</code></pre>
<p>1-1. parseInt()
parseInt()는 정수형의 숫자로 변환한다.</p>
<pre><code class="language-js">parseInt(“27”) //27
parseInt(0033); //27
parseInt(0x1b); //27
parseInt(“ 2”); //2
parseInt(“ 2ㅎ”); //2
parseInt(“ ㅎ2”); //NaN</code></pre>
<p>🌠 <code>parseInt()</code>는 문자열로 된 부분에서 숫자(정수)만 뽑아서 변환해주는것이 특징이고, <code>Number()</code>은 문자열 전체가 숫자일때 소수점까지 숫자타입으로 가져올 수 있다.
<br /></p>
<p>2.&nbsp;문자열로 변환</p>
<pre><code class="language-js">String(123); // &quot;123&quot;
String(true); // &quot;true&quot;
String(null); // &quot;null&quot;
123 + &quot;&quot;; // &quot;123&quot;</code></pre>
<p>2-1.&nbsp;toFixed()
toFixed()의 인자를 넣으면 인자값만큼 반올림하여 소수점을 표현하며 소수점을 넘치는 값이 인자로 들어오며 '0'으로 길이를 맞춘 문자열을 반환한다.</p>
<pre><code class="language-js">var trans = 123.456789;
var roundOff = 99.987654;
trans.toFixed(); //”123&quot;
trans.toFixed(0); //”123&quot;
trans.toFixed(2); //”123.46&quot;
trans.toFixed(8); //”123.45678900&quot;
roundOff.toFixed(2); //”99.99&quot;
roundOff.toFixed(0); //”100&quot;</code></pre>
<p>3.&nbsp;불린으로 변환</p>
<pre><code class="language-js">Boolean(100); //true
Boolean(“1”); //true
Boolean(true); //true
Boolean(Object); //true
Boolean([]); //true
Boolean(0); //false
Boolean(NaN); //false
Boolean(null); //false
Boolean(undefined); //false
Boolean( ); //false

const numb1 = 0;
Boolean(numb1); // false
!!numb1; // false
!numb1; // true</code></pre>
<br />

<hr />
<h2 id="참고자료">참고자료</h2>
<p><a href="https://ko.javascript.info/types">자바스크립트 기본 | 자료형</a></p>