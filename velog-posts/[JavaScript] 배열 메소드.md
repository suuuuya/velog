<p>배열 메소드 정리노트 📚
<br /></p>
<h2 id="✅-foreach-메소드">✅ forEach 메소드</h2>
<blockquote>
<p>배열의 요소를 하나씩 살펴보면서 반복 작업을 하는 메소드</p>
</blockquote>
<p>forEach 메소드는 첫 번째 아규먼트로 콜백 함수를 전달받는다. 콜백 함수의 파라미터에는 각각 배열의 요소, index, 메소드를 호출한 배열이 전달된다.
(index와 array는 생략가능)</p>
<pre><code class="language-js">const numbers = [1, 2, 3];

numbers.forEach((element, index, array) =&gt; {
  console.log(element); // 순서대로 콘솔에 1, 2, 3이 한 줄씩 출력됨.
});</code></pre>
<p><br /><br /></p>
<h2 id="✅-map-메소드">✅ map 메소드</h2>
<blockquote>
<p>forEach와 비슷하게 배열의 요소를 하나씩 살펴보면서 반복 작업을 하는 메소드 </p>
</blockquote>
<p>단, 첫 번째 아규먼트로 전달하는 콜백 함수가 매번 리턴하는 값들을 모아서 새로운 배열을 만들어 리턴하는 특징</p>
<pre><code class="language-js">const numbers = [1, 2, 3];
const twiceNumbers = numbers.map((element, index, array) =&gt; {
  return element * 2;
});

console.log(twiceNumbers); // (3) [2, 4, 6]</code></pre>
<p><br /><br /></p>
<h2 id="✅-filter-메소드">✅ filter 메소드</h2>
<blockquote>
<p>배열의 요소를 하나씩 살펴보면서 콜백함수가 리턴하는 조건과 일치하는 요소만 모아서 새로운 배열을 리턴하는 메소드</p>
</blockquote>
<pre><code class="language-js">const devices = [
  {name: 'GalaxyNote', brand: 'Samsung'},
  {name: 'MacbookPro', brand: 'Apple'},
  {name: 'Gram', brand: 'LG'},
  {name: 'SurfacePro', brand: 'Microsoft'},
  {name: 'ZenBook', brand: 'Asus'},
  {name: 'MacbookAir', brand: 'Apple'},
];

const apples = devices.filter((element, index, array) =&gt; {
  return element.brand === 'Apple';
});

console.log(apples); // (2) [{name: &quot;MacbookPro&quot;, brand: &quot;Apple&quot;}, {name: &quot;MacbookAir&quot;, brand: &quot;Apple&quot;}]
</code></pre>
<p><br /><br /></p>
<h2 id="✅-find-메소드">✅ find 메소드</h2>
<blockquote>
<p>filter 메소드와 비슷하게 동작하지만, 배열의 요소들을 반복하는 중에 콜백함수가 리턴하는 조건과 일치하는 가장 첫번째 요소를 리턴하고 반복을 종료하는 메소드</p>
</blockquote>
<pre><code class="language-js">const devices = [
  {name: 'GalaxyNote', brand: 'Samsung'},
  {name: 'MacbookPro', brand: 'Apple'},
  {name: 'Gram', brand: 'LG'},
  {name: 'SurfacePro', brand: 'Microsoft'},
  {name: 'ZenBook', brand: 'Asus'},
  {name: 'MacbookAir', brand: 'Apple'},
];

const myLaptop = devices.find((element, index, array) =&gt; {
  console.log(index); // 콘솔에는 0, 1, 2까지만 출력됨.
  return element.name === 'Gram';
});

console.log(myLaptop); // {name: &quot;Gram&quot;, brand: &quot;LG&quot;}
</code></pre>
<p><br /><br /></p>
<h2 id="✅-some-메소드">✅ some 메소드</h2>
<blockquote>
<p>배열 안에 콜백함수가 리턴하는 조건을 만족하는 요소가 1개 이상 있는지를 확인하는 메소드</p>
</blockquote>
<p>배열을 반복하면서 모든 요소가 콜백함수가 리턴하는 조건을 만족하지 않는다면 <code>false</code>,
배열을 반복하면서 콜백함수가 리턴하는 조건을 만족하는 요소가 등장한다면 바로 <code>true</code>를 리턴하고 반복을 종료한다.</p>
<pre><code class="language-js">const numbers = [1, 3, 5, 7, 9];

// some: 조건을 만족하는 요소가 1개 이상 있는지
const someReturn = numbers.some((element, index, array) =&gt; {
  console.log(index); // 콘솔에는 0, 1, 2, 3까지만 출력됨.
  return element &gt; 5;
});

console.log(someReturn); // true;
</code></pre>
<p><br /><br /></p>
<h2 id="✅-every-메소드">✅ every 메소드</h2>
<blockquote>
<p>배열 안에 콜백 함수가 리턴하는 조건을 만족하지 않는 요소가 1개 이상 있는지를 확인하는 메소드</p>
</blockquote>
<p>배열을 반복하면서 모든 요소가 콜백함수가 리턴하는 조건을 만족한다면 <code>true</code>,
콜백함수가 리턴하는 조건을 만족하지 않는 요소가 등장한다면 바로 <code>false</code>를 리턴하고 반복을 종료</p>
<pre><code class="language-js">const numbers = [1, 3, 5, 7, 9];

// every: 조건을 만족하지 않는 요소가 1개 이상 있는지
const everyReturn = numbers.every((element, index, array) =&gt; {
  console.log(index); // 콘솔에는 0까지만 출력됨.
  return element &gt; 5;
});

console.log(everyReturn); // false;
</code></pre>
<p><br /><br /></p>
<h2 id="✅-reduce-메소드">✅ reduce 메소드</h2>
<blockquote>
<p>누적값을 계산할 때 활용하는 메소드</p>
</blockquote>
<p>일반적으로 두 개의 파라미터를 활용한다.
매번 실행되는 콜백함수의 리턴값이 다음에 동작할 콜백함수의 첫번째 파라미터로 전달되며, 결과적으로 마지막 콜백함수가 리턴하는 값이 reduce 메소드의 최종 리턴값
이 때 reduce 메소드의 두 번째 파라미터로 전달한 초기값이 첫 번째로 실행될 콜백함수의 가장 첫 번째 파라미터로 전달</p>
<pre><code class="language-js">const numbers = [1, 2, 3, 4];

// reduce
const sumAll = numbers.reduce((accumulator, element, index, array) =&gt; {
  return accumulator + element;
}, 0);

console.log(sumAll); // 10
</code></pre>
<p><br /><br /></p>
<h2 id="✅-sort-메소드">✅ sort 메소드</h2>
<blockquote>
<p>배열 정리 메소드</p>
</blockquote>
<p>아무런 아규먼트도 전달하지 않을 때는 기본적으로 유니코드에 정의된 문자열 순서에 따라 정렬된다.</p>
<pre><code class="language-js">const letters = ['D', 'C', 'E', 'B', 'A'];
const numbers = [1, 10, 4, 21, 36000];

letters.sort();
numbers.sort();

console.log(letters); // (5) [&quot;A&quot;, &quot;B&quot;, &quot;C&quot;, &quot;D&quot;, &quot;E&quot;]
console.log(numbers); // (5) [1, 10, 21, 36000, 4]
</code></pre>
<p>위에 numbers에 sort 메소드를 사용한 것 처럼, 숫자를 정렬할 때 일반적인 오름차순이나 내림차순으로 정렬되지 않는다. 그럴 때 sort 메소드에 아래와 같이 콜백함수를 아규먼트로 작성해준다.</p>
<pre><code class="language-js">const numbers = [1, 10, 4, 21, 36000];

// 오름차순 정렬
numbers.sort((a, b) =&gt; a - b);
console.log(numbers); // (5) [1, 4, 10, 21, 36000]

// 내림차순 정렬
numbers.sort((a, b) =&gt; b - a);
console.log(numbers); // (5) [36000, 21, 10, 4, 1]
</code></pre>
<p>🌠 <strong>sort 메소드를 사용할 때 주의점</strong>
메소드를 실행하는 원본 배열의 요소들을 정렬한다는 점. 그래서 한 번 정렬하고 나면 정렬하기 전의 순서로 다시 되돌릴 수 없다.
<br /><br /></p>
<h2 id="✅-reverse-메소드">✅ reverse 메소드</h2>
<blockquote>
<p>배열의 순서를 뒤집어 주는 메소드</p>
</blockquote>
<p>reverse 메소드는 별도의 파라미터가 존재하지 않기 때문에 단순히 메소드를 호출해주기만 하면 배열의 순서가 뒤집힌다.
🌠 <strong>sort 메소드와 마찬가지로 원본 배열의 요소들을 뒤집어 버린다.</strong></p>
<pre><code class="language-js">const letters = ['a', 'c', 'b'];
const numbers = [421, 721, 353];

letters.reverse();
numbers.reverse();

console.log(letters); // (3) [&quot;b&quot;, &quot;c&quot;, &quot;a&quot;]
console.log(numbers); // (3) [353, 721, 421]
</code></pre>
<br />

<hr />
<br />

<h2 id="✅-map">✅ Map</h2>
<p>Map은 이름이 있는 데이터를 저장한다는 점에서 객체와 비슷하다. 하지만, 할당연산자를 통해 값을 추가하고 점 표기법이나 대괄호 표기법으로 접근하는 일반 객체와 다르게 Map은 메소드를 통해서 값을 추가하거나 접근할 수 있다.
new 키워드를 통해서 Map을 만들 수 있고 아래와 같은 메소드를 통해 Map 안의 여러 값들을 다룰 수 있다.</p>
<pre><code class="language-js">// Map 생성
const codeit = new Map();

// set 메소드
// map.set(key, value): key를 이용해 value를 추가하는 메소드.
codeit.set('title', '문자열 key');
codeit.set(2017, '숫자형 key');
codeit.set(true, '불린형 key');

// get 메소드
// map.get(key): key에 해당하는 값을 얻는 메소드. key가 존재하지 않으면 undefined를 반환.
console.log(codeit.get(2017)); // 숫자형 key
console.log(codeit.get(true)); // 불린형 key
console.log(codeit.get('title')); // 문자열 key

// has 메소드
// map.has(key): key가 존재하면 true, 존재하지 않으면 false를 반환하는 메소드.
console.log(codeit.has('title')); // true
console.log(codeit.has('name')); // false

// size 프로퍼티
// map.size: 요소의 개수를 반환하는 프로퍼티. (메소드가 아닌 점 주의! 배열의 length 프로퍼티와 같은 역할)
console.log(codeit.size); // 3

// delete 메소드
// map.delete(key): key에 해당하는 값을 삭제하는 메소드.
codeit.delete(true);
console.log(codeit.get(true)); // undefined
console.log(codeit.size); // 2

// clear 메소드
// map.clear(): Map 안의 모든 요소를 제거하는 메소드.
codeit.clear();
console.log(codeit.get(2017)); // undefined
console.log(codeit.size); // 0
</code></pre>
<p><br /><br /></p>
<h2 id="✅-set">✅ Set</h2>
<p>Set은 여러 개의 값을 순서대로 저장한다는 점에서 배열과 비슷하다. 하지만, 배열의 메소드는 활용할 수 없고 Map과 비슷하게 Set만의 메소드를 통해서 값을 다루는 특징이 있는데, Map과 마찬가지로 new 키워드로 Set을 만들 수 있고 아래와 같은 메소드를 통해 Set 안의 여러 값들을 다룰 수 있다.</p>
<pre><code class="language-js">// Set 생성
const members = new Set();

// add 메소드
// set.add(value): 값을 추가하는 메소드. (메소드를 호출한 자리에는 추가된 값을 가진 Set 자신을 반환.)
members.add('영훈'); // Set(1) {&quot;영훈&quot;}
members.add('윤수'); // Set(2) {&quot;영훈&quot;, &quot;윤수&quot;}
members.add('동욱'); // Set(3) {&quot;영훈&quot;, &quot;윤수&quot;, &quot;동욱&quot;}
members.add('태호'); // Set(4) {&quot;영훈&quot;, &quot;윤수&quot;, &quot;동욱&quot;, &quot;태호&quot;}

// has 메소드
// set.has(value): Set 안에 값이 존재하면 true, 아니면 false를 반환하는 메소드.
console.log(members.has('동욱')); // true
console.log(members.has('현승')); // false

// size 프로퍼티
// set.size: 요소의 개수를 반환하는 프로퍼티. (메소드가 아닌 점 주의! 배열의 length 프로퍼티와 같은 역할)
console.log(members.size); // 4

// delete 메소드
// set.delete(value): 값을 제거하는 메소드. (메소드를 호출한 자리에는 셋 내에 값이 있어서 제거에 성공하면 true, 아니면 false를 반환.)
members.delete('종훈'); // false
console.log(members.size); // 4
members.delete('태호'); // true
console.log(members.size); // 3

// clear 메소드
// set.clear(): Set 안의 모든 요소를 제거하는 메소드.
members.clear();
console.log(members.size); // 0
</code></pre>
<p>🌠 <strong>특이점</strong>
일반 객체는 프로퍼티 네임, Map은 get메소드, 그리고 배열은 index를 통해서 개별 값에 접근할 수 있었는데, Set에는 개별 값에 바로 접근하는 방법이 없다.</p>
<p>그래서 아래 코드와 같이 반복문을 통해서 전체요소를 한꺼번에 다룰 때 반복되는 그 순간에 개별적으로 접근할 수가 있다.</p>
<pre><code class="language-js">// Set 생성
const members = new Set();

// add 메소드
members.add('영훈'); // Set(1) {&quot;영훈&quot;}
members.add('윤수'); // Set(2) {&quot;영훈&quot;, &quot;윤수&quot;}
members.add('동욱'); // Set(3) {&quot;영훈&quot;, &quot;윤수&quot;, &quot;동욱&quot;}
members.add('태호'); // Set(4) {&quot;영훈&quot;, &quot;윤수&quot;, &quot;동욱&quot;, &quot;태호&quot;}

for (const member of members) {
  console.log(member); // 영훈, 윤수, 동욱, 태호가 순서대로 한 줄 씩 콘솔에 출력됨.
}
</code></pre>
<p><strong>🌠 이런 특징을 가지고도 Set이 유용하게 사용되는 경우</strong>
중복을 허용하지 않는 값들을 모을 때, Set은 중복되는 값을 허용하지 않는 독특한 특징이 있다. Set 객체에 요소를 추가할 때 이미 Set 객체 안에 있는 값(중복된 값)을 추가하려고 하면 그 값은 무시되는 특징이 있다.</p>
<p>처음 Set을 생성할 때 아규먼트로 배열을 전달할 수가 있는데, 이런 특징을 활용해서 배열 내에서 중복을 제거한 값들의 묶음을 만들 때 Set을 활용할 수 있다.</p>
<pre><code class="language-js">const numbers = [1, 3, 4, 3, 3, 3, 2, 1, 1, 1, 5, 5, 3, 2, 1, 4];
const uniqNumbers = new Set(numbers);

console.log(uniqNumbers); // Set(5) {1, 3, 4, 2, 5}
</code></pre>
<br />

<hr />
<h2 id="참고자료">참고자료</h2>
<p>코드잇 | 모던 자바스크립트 배열 메소드 종합 정리</p>