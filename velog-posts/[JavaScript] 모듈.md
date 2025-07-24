<h2 id="✅-모듈">✅ 모듈</h2>
<blockquote>
<p>코드를 파일 단위로 나눠서 관리하고 재사용할 수 있게 해주는 기능</p>
</blockquote>
<h4 id="필요성">필요성</h4>
<p>복잡하고 많은 양의 코드를 기능에 따라 각각의 파일로 나눠 관리하면 . . </p>
<p>✔️ 코드를 좀 더 효율적으로 관리 (파일 분리, 가독성 향상)
✔️ 비슷한 기능이 필요할 때 다른 프로그램에서 재사용 (중복 제거)
✔️ 전역 변수 충돌 방지 (모듈 범위는 파일 내부 스코프)</p>
<p><br /><br /></p>
<h2 id="✅-모듈-스코프">✅ 모듈 스코프</h2>
<blockquote>
<p>ES Modules에서 각 모듈(파일)마다 독립된 스코프(scope)를 가지는 것.</p>
</blockquote>
<p>🌠 <strong>모듈은 파일 안에서 모듈 파일만의 독립적인 스코프를 가지고 있어야한다.</strong></p>
<p>모듈 파일 안에서 선언한 변수는 외부에서 자유롭게 접근할 수 없도록 막아야 하는데, HTML파일에서 자바스크립트 파일을 불러올 때 모듈 스코프를 갖게 하려면
script태그에 type속성을 module이라는 값으로 지정해 주어야 한다.</p>
<pre><code class="language-html">&lt;body&gt;
  &lt;script type=&quot;module&quot; src=&quot;index.js&quot;&gt;&lt;/script&gt;
&lt;/body&gt;</code></pre>
<p><br /><br /></p>
<h2 id="✅-모듈-문법">✅ 모듈 문법</h2>
<blockquote>
<p>자바스크립트의 모듈 문법은 <code>export</code>와 <code>import</code>.</p>
</blockquote>
<p>모듈 스코프를 가진 파일에서 <strong>외부로 내보내고자 하는 변수나 함수를</strong> <code>export</code> 키워드를 통해 내보내고, <strong>모듈 파일에서 내보낸 변수나 함수들은 다른 파일에서 **<code>import</code></strong> 키워드를 통해 가져온다.**</p>
<pre><code class="language-js">// printer.js
export const title = 'CodeitPrinter';

export function print(value) {
  console.log(value);
};

// ---------------------------------------

// index.js
import { title, print } from './printer.js';

print(title);</code></pre>
<br />

<h3 id="이름-바꿔-import-하기">이름 바꿔 import 하기</h3>
<blockquote>
<p>import 키워드를 통해 모듈을 불러올 때 as 키워드를 활용하면 import하는 대상들의 이름을 변경할 수 있다.</p>
</blockquote>
<p>✔️ 함수 이름을 조금 더 간결한 이름으로 바꾸거나, 
✔️ 더 구체적으로 바꾸고 싶을 때 활용</p>
<p>이름을 바꿔서 import 하면 여러 파일에서 불러오는 대상들의 이름이 중복되는 문제를 해결할 수도 있다.</p>
<pre><code class="language-js">import { title as printerTitle, print, printArr } from './printer.js';
import { title, data as members } from './members.js';

printer(title);
arrPrinter(members);
</code></pre>
<br />

<h3 id="한꺼번에-import-하기">한꺼번에 import 하기</h3>
<blockquote>
<p>import할 때 와일드카드 문자(*)와 as를 활용하면 모듈 파일에서 export하는 모든 대상을 하나의 객체로 불러올 수 있다.</p>
</blockquote>
<pre><code class="language-js">import * as printerJS from './printer.js';

console.log(printerJS.title); // CodeitPrinter
console.log(printerJS.print); // ƒ print(value) { console.log(value); }
</code></pre>
<br />

<h3 id="한꺼번에-export-하기">한꺼번에 export 하기</h3>
<blockquote>
<p>변수나 함수 앞에 매번 export 키워드를 붙일 수도 있지만, 선언된 변수나 함수를 하나의 객체로 모아 한꺼번에 내보낼 수도 있다.</p>
</blockquote>
<p>이때 as 키워드를 활용하면 이름을 변경해서 export할 수도 있다.</p>
<pre><code class="language-js">const title = 'CodeitPrinter';

function print(value) {
  console.log(value);
}

function printArr(arr) {
  arr.forEach((el, i) =&gt; {
    console.log(`${i + 1}. ${el}`);
  });
}

export { title as printerTitle, print, printArr };
</code></pre>
<br />

<h3 id="default-export">default export</h3>
<blockquote>
<p>export를 할 때 default 키워드를 함께 사용하면 모듈 파일에서 기본적으로 export할 대상을 정할 수 있다.</p>
</blockquote>
<p>일반적으로 모듈 파일에서 export 대상이 하나라면, 이 default 키워드를 함께 활용하는 것이 조금 더 간결한 코드를 구성하는데 도움이 되는데 . .</p>
<pre><code class="language-js">const title = 'CodeitPrinter';

function print(value) {
  console.log(value);
}

export default print;
</code></pre>
<p>default export는 import할 때 기본적으로 다음과 같이 불러올 수 있지만,</p>
<pre><code class="language-js">import { default as printerJS } from './printer.js';

console.log(printerJS.title); // CodeitPrinter
console.log(printerJS.print); // ƒ print(value) { console.log(value); }
</code></pre>
<p>다음과 같이 축약형 문법으로 import 할 수도 있기 때문.</p>
<pre><code class="language-js">import printerJS from './printer.js';

console.log(printerJS.title); // CodeitPrinter
console.log(printerJS.print); // ƒ print(value) { console.log(value); }
</code></pre>
<p><br /><br /></p>
<h2 id="✅-다양한-방법으로-활용해보기">✅ 다양한 방법으로 활용해보기</h2>
<p>다양한 방식으로 작성될 수 있다.
<br /><br /></p>
<p>✔️ export를 할 때도 <strong>선언문을 export</strong>하거나</p>
<pre><code class="language-js">export const title = 'Module';</code></pre>
<br />

<p>✔️ 선언된 변수나 함수를 <strong>코드 블록으로 묶어서 export</strong>할 수도 있고,</p>
<pre><code class="language-js">const printer = (value) =&gt; {
  console.log(value);
};

const arrPrinter = (arr) =&gt; {
  arr.forEach((el, i) =&gt; {
    console.log(`${i + 1}. ${el}`);
  })
};

export { printer, arrPrinter };</code></pre>
<br />

<p>✔️ as 키워드를 통해 <strong>이름을 변경해서 export</strong>를 할 수 있다.</p>
<pre><code class="language-js">const printer = (value) =&gt; {
  console.log(value);
};

const arrPrinter = (arr) =&gt; {
  arr.forEach((el, i) =&gt; {
    console.log(`${i + 1}. ${el}`);
  })
};

export { printer as namedPrinter, arrPrinter };
</code></pre>
<br />

<p>✔️ default 키워드를 통해 <strong>표현식을 export하는 방법</strong></p>
<pre><code class="language-js">const title = 'Module';

export default title;
</code></pre>
<br />

<p>✔️ <strong>여러 대상을 객체 값으로 모아 내보내는 방식</strong></p>
<pre><code class="language-js">const title = 'Module';

const printer = (value) =&gt; {
  console.log(value);
};

const arrPrinter = (arr) =&gt; {
  arr.forEach((el, i) =&gt; {
    console.log(`${i + 1}. ${el}`);
  })
};

export default { title, printer, arrPrinter };
</code></pre>
<br />

<p>✔️ import도 import 키워드 이후에 중괄호를 감싸면, 아래 코드 처럼  <strong>모듈 파일에서export하는 항목들을 선택적으로 불러오기</strong></p>
<pre><code class="language-js">import { title, data } from './modules.js';</code></pre>
<br />

<p>✔️ as 키워드를 통해서 아래 코드 처럼 <strong>이름 바꾸기</strong></p>
<pre><code class="language-js">import { title as moduleTitle, data } from './modules.js';
</code></pre>
<br />

<p>✔️ 와일드카드 문자(<em>)를 통해서 아래 코드 처럼 *</em>export된 항목들을 모두 불러오기**</p>
<pre><code class="language-js">import * as modules from './modules.js';
</code></pre>
<br />

<p>✔️ default export된 대상을 import할 때 <strong>축약형으로 불러오기</strong></p>
<pre><code class="language-js">import { defult as modules } from './modules.js';
// 축약형
import modules from './modules.js';</code></pre>
<br />

<p>✔️ 응용 예</p>
<pre><code class="language-js">// (modules.js)
import module1 from './sub-module1.js';
import module2 from './sub-module2.js';
import module3 from './sub-module3.js';

export { module1, module2, module3 };


// -----------------------------------


// index.js
import { module1, module2, module3 } from 'modules.js';

</code></pre>
<hr />
<h2 id="참고자료">참고자료</h2>
<p>코드잇 | 자바스크립트 모듈 토픽</p>