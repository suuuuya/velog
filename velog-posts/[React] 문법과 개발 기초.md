<h2 id="✅-jsx-문법">✅ JSX 문법</h2>
<blockquote>
<p>리액트에서 지원하는 문법으로, <strong>자바스크립트와 HTML을 함께 사용하는 문법이다.</strong></p>
</blockquote>
<p>JSX는 자바스크립트의 확장 문법이기 때문에 HTML 문법을 완전히 그대로 사용할 수는 없다.</p>
<br />

<h3 id="❗html과-다른-속성명">❗HTML과 다른 속성명</h3>
<p>속성명은 카멜 케이스로 작성하기!</p>
<blockquote>
<p>JSX 문법에서도 태그에 속성을 지정해 줄 수 있다. 단, 여러 단어가 조합된 몇몇 속성들을 사용할 때는 반드시 카멜 케이스(Camel Case)로 작성해야 한다.</p>
</blockquote>
<br />

<h4 id="📄-이벤트-핸들러">📄 이벤트 핸들러</h4>
<p>소문자로 작성했던 이벤트 핸들러들은 <code>카멜 표기법</code>으로 작정해준다.</p>
<pre><code class="language-jsx">import ReactDOM from 'react-dom';

ReactDOM.render(
  &lt;button onClick= ... &gt;클릭!&lt;/button&gt;,
  document.getElementById('root')
);

root.render(
&lt;form&gt;
  &lt;label htmlFor=&quot;name&quot;&gt;이름&lt;/label&gt;
  &lt;input id=&quot;name&quot; type=&quot;text&quot; onBlur=&quot;&quot; onFocus=&quot;&quot; onMouseDown=&quot;&quot;&gt;
&lt;/form&gt;
);</code></pre>
<p>예외적으로 HTML에서 비표준 속성을 다룰 때 활용하는 <code>data-*</code> 속성은 카멜 케이스(Camel Case)가 아니라 기존의 HTML 문법 그대로 작성한다.</p>
<pre><code class="language-js">import ReactDOM from 'react-dom';

ReactDOM.render(
  &lt;div&gt;
    상태 변경: 
    &lt;button className=&quot;btn&quot; data-status=&quot;대기중&quot;&gt;대기중&lt;/button&gt;
    &lt;button className=&quot;btn&quot; data-status=&quot;진행중&quot;&gt;진행중&lt;/button&gt;
    &lt;button className=&quot;btn&quot; data-status=&quot;완료&quot;&gt;완료&lt;/button&gt;
  &lt;/div&gt;,
  document.getElementById('root')
);
</code></pre>
<br />

<h3 id="❗자바스크립트-예약어와-같은-속성명은-사용할-수-없다">❗자바스크립트 예약어와 같은 속성명은 사용할 수 없다!</h3>
<p>JSX 문법도 결국은 자바스크립트 문법이기 때문에, for나 class처럼 자바스크립트의 문법에 해당하는 예약어와 똑같은 이름의 속성명은 사용할 수 없다.</p>
<p>🌠 <a href="https://ko.legacy.reactjs.org/docs/dom-elements.html#differences-in-attributes">React 공식 문서 | 어트리뷰트의 차이</a></p>
<h4 id="📄-class">📄 class</h4>
<p>JSX의 class는 객체 지향의 개념으로, 어떤 요소의 클래스를 선언할 때 class 키워드를 사용하기 때문에...</p>
<pre><code class="language-jsx">class name{
    ...
}</code></pre>
<p>클래스를 만들어주려면 <code>className</code>으로 작성해준다.</p>
<pre><code class="language-jsx">root.render(&lt;h1 className=&quot;hello&quot;&gt;하이&lt;/h1&gt;);</code></pre>
<br />

<h4 id="📄-for">📄 for</h4>
<p>자바스크립트에서 반복문에 for 키워드를 사용하기 때문에, HTML에 for 속성을 사용하려면, <code>htmlFor</code>라고 작성해준다.</p>
<pre><code class="language-jsx">root.render(
&lt;form&gt;
  &lt;label htmlFor=&quot;name&quot;&gt;이름&lt;/label&gt;
  &lt;input id=&quot;name&quot; type=&quot;text&quot;&gt;
&lt;/form&gt;
);</code></pre>
<br />

<h3 id="❗반드시-하나의-요소로-감싸기">❗반드시 하나의 요소로 감싸기</h3>
<h4 id="📄-프래그먼트fragment">📄 프래그먼트(Fragment)</h4>
<p>JSX 요소들은 반드시 하나의 태그로 감싸줘야한다.</p>
<pre><code class="language-jsx">// X
root.render(
  &lt;p&gt;단락&lt;/p&gt;
  &lt;p&gt;단락&lt;/p&gt;,
  ...
);

// O
root.render(
  &lt;div&gt;
    &lt;p&gt;단락&lt;/p&gt;
    &lt;p&gt;단락&lt;/p&gt;
  &lt;/div&gt;,
  ...
);</code></pre>
<p>💡 <strong>그런데, <code>div</code> 태그를 사용하고 싶지 않다면?</strong>
☑️ 리액트에서 제공하는 <code>프래그먼트</code>를 사용한다.</p>
<p>잘 활용하면 불필요한 태그 사용을 줄일 수 있다.</p>
<pre><code class="language-jsx">// fragment를 사용하면 react 패키지에서 자동으로 import 해준다.
import { fragment } from 'react';

root.render(
  &lt;fragment&gt;
    &lt;p&gt;단락&lt;/p&gt;
    &lt;p&gt;단락&lt;/p&gt;
  &lt;/fragment&gt;,
  ...
);</code></pre>
<p>🌠 <strong>빈 태그로 감싸는 단축 문법</strong>
긴 이름 사용보다는 이름 없는 태그로 축약해서 깔끔하게 사용하기도 한다.
아래와 같이 사용하면 프래그먼트를 import하지 않아도 된다.</p>
<pre><code class="language-jsx">root.render(
  &lt;&gt;
    &lt;p&gt;단락&lt;/p&gt;
    &lt;p&gt;단락&lt;/p&gt;
  &lt;/&gt;,
  ...
);</code></pre>
<br />

<h3 id="❗자바스크립트-표현식-넣기">❗자바스크립트 표현식 넣기</h3>
<p>JSX 문법에서 중괄호({})를 활용하면 자바스크립트 표현식을 넣을 수 있다.</p>
<pre><code class="language-js">import ReactDOM from 'react-dom';

const product = '맥북';

ReactDOM.render(
  &lt;h1&gt;나만의 {product} 주문하기&lt;/h1&gt;,
  document.getElementById('root')
);</code></pre>
<p>이런 부분들을 잘 활용하면, 아래 코드처럼 중괄호 안에서 문자열을 조합할 수도 있고 변수에 이미지 주소를 할당해서 img 태그의 src 속성값을 전달해 줄 수도 있고, 이벤트 핸들러를 좀 더 편리하게 등록할 수도 있다.</p>
<pre><code class="language-js">import ReactDOM from 'react-dom';

const product = 'MacBook';
const model = 'Air';
const imageUrl = 'https://upload.wikimedia.org/wikipedia/commons/thumb/1/1e/MacBook_with_Retina_Display.png/500px-MacBook_with_Retina_Display.png'

function handleClick(e) {
  alert('곧 도착합니다!');
}

ReactDOM.render(
  &lt;&gt;
    &lt;h1&gt;{product + ' ' + model} 주문하기&lt;/h1&gt;
    &lt;img src={imageUrl} alt=&quot;제품 사진&quot; /&gt;
    &lt;button onClick={handleClick}&gt;확인&lt;/button&gt;
  &lt;/&gt;,
  document.getElementById('root')
);
</code></pre>
<br />

<p>🌠 <strong>단, JSX 문법에서 중괄호는 자바스크립트 표현식을 다룰 때 활용하기 때문에, 중괄호 안에서 for, if문 등의 문장은 다룰 수 없다는 점.</strong>
<br /><br /></p>
<h2 id="✅-컴포넌트-문법">✅ 컴포넌트 문법</h2>
<h3 id="리액트-엘리먼트">리액트 엘리먼트</h3>
<blockquote>
<p>리액트 엘리먼트는 리액트로 화면을 그려내는데 가장 기본적인 요소.</p>
</blockquote>
<p>아래와 같은 객체를 리액트 엘리먼트라고 부른다.</p>
<pre><code class="language-js">import ReactDOM from 'react-dom';

const element = &lt;h1&gt;안녕 리액트!&lt;/h1&gt;;
console.log(element);
ReactDOM.render(element, document.getElementById('root'));


-----------------------
// JSX 문법으로 작성한 요소는 결과적으로 자바스크립트 객체가 된다.
//{$$typeof: Symbol(react.element), type: &quot;h1&quot;, key: null, ref: null, props: {…}, …}
</code></pre>
<p>이런 리액트 엘리먼트를 <code>ReactDOM.render</code> 함수의 아규먼트로 전달하게 되면,
리액트가 객체 형태 값을 해석해서 HTML 형태로 브라우저에 띄워줌
<br /><br /></p>
<h3 id="리액트-컴포넌트">리액트 컴포넌트</h3>
<blockquote>
<p>리액트 컴포넌트는 리액트 엘리먼트를 조금 더 자유롭게 다루기 위한 하나의 문법</p>
</blockquote>
<p>컴포넌트를 만드는 가장 간단한 방법은 자바스크립트의 함수를 활용하는 것.</p>
<p>아래의 <code>Hello</code> 함수가 바로 하나의 컴포넌트인데, 컴포넌트 함수 이름을 통해 하나의 태그처럼 활용할 수가 있다.</p>
<pre><code class="language-js">import ReactDOM from 'react-dom';

function Hello() {
  return &lt;h1&gt;안녕 리액트&lt;/h1&gt;;
}

const element = (
  &lt;&gt;
    &lt;Hello /&gt;
    &lt;Hello /&gt;
    &lt;Hello /&gt;
  &lt;/&gt;
);

ReactDOM.render(element, document.getElementById('root'));
</code></pre>
<br />

<h4 id="🌠-이런-특성을-모듈-문법으로-활용하면-훨씬-더-독립적으로-컴포넌트-특성에-집중해서-코드를-작성할-수가-있다">🌠 이런 특성을 모듈 문법으로 활용하면 훨씬 더 독립적으로 컴포넌트 특성에 집중해서 코드를 작성할 수가 있다.</h4>
<p>☑️ 한가지 주의해야할 부분은 <strong>리액트 컴포넌트의 이름은 반드시 첫 글자를 대문자로 작성</strong>해야한다는 것!</p>
<h4 id="📄-dicejs">📄 Dice.js</h4>
<pre><code class="language-js">import diceBlue01 from './assets/dice-blue-1.svg';

function Dice() {
  return &lt;img src={diceBlue01} alt=&quot;주사위&quot; /&gt;;
}

export default Dice;
</code></pre>
<h4 id="📄-appjs">📄 App.js</h4>
<pre><code class="language-js">import Dice from './Dice';

function App() {
  return (
    &lt;div&gt;
      &lt;Dice /&gt;
    &lt;/div&gt;
  );
}

export default App;
</code></pre>
<hr />
<h2 id="✅-props">✅ Props</h2>
<blockquote>
<p>Props는 Properties의 약자</p>
</blockquote>
<p><strong>컴포넌트에 지정한 속성들을 Props라고 부른다.</strong></p>
<p>컴포넌트에 속성을 지정해주면 각 속성이 하나의 객체로 모여서 컴포넌트를 정의한 함수의 첫 번째 파라미터로 전달된다.</p>
<h4 id="📄-dicejs-1">📄 Dice.js</h4>
<pre><code class="language-js">import diceBlue01 from './assets/dice-blue-1.svg';

function Dice(props) {
  console.log(props)
  return &lt;img src={diceBlue01} alt=&quot;주사위&quot; /&gt;;
}

export default Dice;

------------------------
// { color: &quot;blue&quot; }
</code></pre>
<h4 id="📄-appjs-1">📄 App.js</h4>
<pre><code class="language-js">import Dice from './Dice';

function App() {
  return (
    &lt;div&gt;
      &lt;Dice color=&quot;blue&quot; /&gt;
    &lt;/div&gt;
  );
}

export default App;
</code></pre>
<p>props 값을 활용하면, 똑같은 컴포넌트라도 전달된 속성값에 따라 서로 다른 모습을 그려낼 수도 있게 된다.</p>
<h4 id="🌠-심화">🌠 심화</h4>
<h4 id="📄-dicejs-2">📄 Dice.js</h4>
<pre><code class="language-js">import diceBlue01 from './assets/dice-blue-1.svg';
import diceBlue02 from './assets/dice-blue-2.svg';

import diceRed01 from './assets/dice-red-1.svg';
import diceRed02 from './assets/dice-red-2.svg';


const DICE_IMAGES = {
  blue: [diceBlue01, diceBlue02],
  red: [diceRed01, diceRed02],
};

function Dice(props) {
  const src = DICE_IMAGES[props.color][props.num - 1];
  const alt = `${props.color} ${props.num}`;
  return &lt;img src={src} alt={alt} /&gt;;
}

export default Dice;
</code></pre>
<h4 id="📄-appjs-2">📄 App.js</h4>
<pre><code class="language-js">import Dice from './Dice';

function App() {
  return (
    &lt;div&gt;
      &lt;Dice color=&quot;red&quot; num={2} /&gt;
    &lt;/div&gt;
  );
}

export default App;

</code></pre>
<br />

<h4 id="🌠-destructuring-문법">🌠 Destructuring 문법</h4>
<blockquote>
<p>배열이나 객체에서 값을 쉽게 추출하고 변수에 할당하는 방법</p>
</blockquote>
<h4 id="배열-destructuring-예시">배열 Destructuring 예시</h4>
<pre><code class="language-js">const numbers = [10, 20, 30];

// ✅ 배열에서 값 꺼내는 전통적인 방법
const first = numbers[0];
const second = numbers[1];
const third = numbers[2];

console.log(first, second, third);  // 10 20 30
----------------------------
// ✅ 더 간편한 방법
const numbers = [10, 20, 30];

// 배열 디스트럭처링 사용
// [first, second, third] 이렇게 배열 모양을 쓰고, 
// 등호 = 오른쪽에 배열을 넣어주면, 배열의 값을 변수에 할당
const [first, second, third] = numbers;

console.log(first, second, third);  // 10 20 30
----------------------------
const numbers = [10, 20, 30, 40, 50];

// ✅ 첫 번째 값만 받고, 나머지는 나머지 배열로 받기
const [first, ...rest] = numbers;

console.log(first);  // 10
console.log(rest);   // [20, 30, 40, 50]</code></pre>
<h4 id="객체-destructuring-예시">객체 Destructuring 예시</h4>
<pre><code class="language-js">const person = {
  name: 'Alice',
  age: 25,
  job: 'Engineer'
};

// ✅ 객체에서 값 꺼내는 전통적인 방법
const name = person.name;
const age = person.age;
const job = person.job;

console.log(name, age, job);  // Alice 25 Engineer
----------------------------
const person = {
  name: 'Alice',
  age: 25,
  job: 'Engineer'
};

// ✅ 객체 디스트럭처링 사용
const { name, age, job } = person;

console.log(name, age, job);  // Alice 25 Engineer
----------------------------
const person = {
  name: 'Alice',
  age: 25,
  job: 'Engineer'
};

// ✅ name과 age만 받고, 나머지는 나머지 객체로 받기
const { name, age, ...rest } = person;

console.log(name);  // Alice
console.log(age);   // 25
console.log(rest);  // { job: 'Engineer' }</code></pre>
<br />

<p>위와 같이 Destructuring 문법을 활용해서 간결하게 코드 작성해보기!</p>
<pre><code class="language-js">import diceBlue01 from './assets/dice-blue-1.svg';
import diceBlue02 from './assets/dice-blue-2.svg';
// ...
import diceRed01 from './assets/dice-red-1.svg';
import diceRed02 from './assets/dice-red-2.svg';
// ...

const DICE_IMAGES = {
  blue: [diceBlue01, diceBlue02],
  red: [diceRed01, diceRed02],
};

function Dice({ color = 'blue', num = 1 }) {
  const src = DICE_IMAGES[color][num - 1];
  const alt = `${color} ${num}`;
  return &lt;img src={src} alt={alt} /&gt;;
}

export default Dice;
</code></pre>
<p><br /><br /></p>
<h2 id="✅-children">✅ Children</h2>
<p><code>props</code>에는 <code>children</code>이라는 프로퍼티(prop,프롭)가 있다.</p>
<blockquote>
<p> 컴포넌트를 작성할 때 <strong>여는 태그와 닫는 태그의 형태로 작성</strong>하면, 그 안에 작성된 코드가 바로 이 <strong>children</strong> 값에 담긴다.</p>
</blockquote>
<p><code>children</code>을 활용하면 단순히 텍스트만 작성하는 걸 넘어서 컴포넌트 안에 컴포넌트를 작성할 수도 있고, 컴포넌트 안에 복잡한 태그들을 더 작성할 수도 있다.</p>
<h3 id="🌠-활용-예시">🌠 <strong>활용 예시</strong></h3>
<p>☑️ <strong>어떤 정보를 전달할 때</strong>
일반적인 <code>props</code>의 속성값을 주로 활용</p>
<p>☑️ <strong>화면에 보여질 모습을 조금 더 직관적인 코드로 작성하고자 할 때</strong>
<code>children</code> 값을 활용</p>
<h4 id="📄-buttonjs">📄 Button.js</h4>
<pre><code class="language-js">function Button({ children }) {
  return &lt;button&gt;{children}&lt;/button&gt;;
}

export default Button;
</code></pre>
<h4 id="📄-appjs-3">📄 App.js</h4>
<pre><code class="language-js">import Button from './Button';
import Dice from './Dice';

function App() {
  return (
    &lt;div&gt;
      &lt;div&gt;
        &lt;Button&gt;던지기&lt;/Button&gt;
        &lt;Button&gt;처음부터&lt;/Button&gt;
      &lt;/div&gt;
      &lt;Dice color=&quot;red&quot; num={2} /&gt;
    &lt;/div&gt;
  );
}

export default App;</code></pre>
<br />


<h2 id="✅-state">✅ State</h2>
<blockquote>
<p>컴포넌트의 상태를 관리하는 객체로, 상태가 변할 때마다 컴포넌트는 자동으로 다시 렌더링 되어 UI가 업데이트된다.</p>
</blockquote>
<h4 id="usestate">useState</h4>
<p><strong>state</strong>를 만들고 <strong>state</strong>를 바꾸기 위해서는 <code>useState</code>라는 함수를 활용해야 한다.
<br /></p>
<p>보통 아래와 같이 <strong>Destructuring 문법</strong>으로 작성하는데, <code>useState</code> 함수가 <u>초깃값을 아규먼트로 받고</u> 그에 따른 <u>실행 결과로 요소 2개를 가진 배열의 형태로 리턴</u>을 하기 때문이다.</p>
<p>☑️ *<em>state의 setter 함수의 이름은 일반적으로 state 이름 앞에 set을 붙여서 짓는다.
*</em></p>
<pre><code class="language-js">import { useState } from 'react';
// 첫 번째 요소가 바로 state이고, 두 번째 요소가 이 state를 바꾸는 setter 함수
// 첫 번째 변수는 원하는 state의 이름(num)을 지어주고, 
// 두 번째 변수에는 state 이름 앞에 set을 붙인 다음 카멜 케이스로 이름을 지어주는 것(setNum)이 일반적
const [num, setNum] = useState(1);
</code></pre>
<br />

<p><strong>state</strong>는 변수에 새로운 값을 할당하는 방식으로 변경하는 것이 아니라 이 <code>setter</code> 함수를 활용해야 하는데, <code>setter</code> 함수는 호출할 때 전달하는 아규먼트 값으로 <strong>state</strong> 값을 변경해 줍니다.</p>
<p>그래서 아래 코드처럼 <strong>setter</strong> 함수를 활용해서 이벤트 핸들러를 등록해두면, 이벤트가 발생할 때마다 상태가 변하면서 화면이 새로 그려진다.</p>
<pre><code class="language-js">import { useState } from 'react';
import Button from './Button';
import Dice from './Dice';

function App() {
  const [num, setNum] = useState(1);

  const handleRollClick = () =&gt; {
    setNum(3); // num state를 3으로 변경!
  };

  const handleClearClick = () =&gt; {
    setNum(1); // num state를 1로 변경!
  };

  return (
    &lt;div&gt;
      &lt;Button onClick={handleRollClick}&gt;던지기&lt;/Button&gt;
      &lt;Button onClick={handleClearClick}&gt;처음부터&lt;/Button&gt;
      &lt;Dice color=&quot;red&quot; num={num} /&gt;
    &lt;/div&gt;
  );
}

export default App;
</code></pre>
<br />

<h3 id="참조형-state">참조형 State</h3>
<p>참조형 <strong>state</strong>를 활용할 때는 반드시 새로운 참조형 값을 만들어 <strong>state</strong>를 변경해야 한다.</p>
<p>☑️** 가장 간단한 방법은 Spread 문법(...) 을 활용하는 것**</p>
<pre><code class="language-js">const [gameHistory, setGameHistory] = useState([]);

  const handleRollClick = () =&gt; {
    const nextNum = random(6);
    setGameHistory([...gameHistory, nextNum]); // state가 제대로 변경된다!
  };</code></pre>