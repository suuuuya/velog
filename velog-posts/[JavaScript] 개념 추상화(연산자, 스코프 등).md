<h2 id="✅복합-할당-연산자">✅복합 할당 연산자</h2>
<p>가독성, 코드량 감소, 유지보수 용이</p>
<pre><code class="language-js">x = x + 2; // x에 2을 더해서 다시 x에 할당
x += 2;    // 복합 할당 연산자 - 위와 같은 의미

// 예제
let x = 10;
x += 5;  // 15
x -= 2;  // 13
x *= 3;  // 39</code></pre>
<p>위와 같이 <code>+=</code>, <code>-=</code>, <code>*=</code>, <code>/=</code>, <code>%=</code> 등의 복합 할당 연산자를 사용하면, 더 간결한 표현으로 연산을 처리할 수 있다.
<br /></p>
<h2 id="✅증가-감소-연산자">✅증가 감소 연산자</h2>
<p>값을 1씩 증가시키거나 감소시킬 때</p>
<pre><code class="language-js">let score = 10;

score++;  // score의 값을 1 증가시킴 (score = score + 1과 같은 의미)
score--;  // score의 값을 1 감소시킴 (score = score - 1과 같은 의미)</code></pre>
<br />

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
<br />


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


<h2 id="✅-변수의-scope">✅ 변수의 scope</h2>
<pre><code class="language-js">// scope: 범위 영역
var globalVar = &quot;전역 변수&quot;; // 글로벌 변수, 전역 변수

function myFunction() { // 블록문
  var functionVar = &quot;함수 내부 변수&quot;; // 로컬 변수, 지역 변수, 함수 스코프
  console.log(globalVar); // 접근 가능
  console.log(functionVar); // 접근 가능

  if (true) {
    let blockVar = &quot;블록 내부 변수&quot;; // 블록 스코프
    console.log(blockVar); // 접근 가능
    console.log(functionVar); // 접근 가능
  }
  // console.log(blockVar); // 접근 불가
}

myFunction();
console.log(globalVar); // 접근 가능
// console.log(functionVar); // 접근 불가</code></pre>
<br />



<hr />
<p>코드잇 프로그래밍 핵심 개념 | 추상화 토픽</p>