<p>그리드 레이아웃은 Flex와 다르게 콘텐츠를 행과 열에 배치해서 복잡한 레이아웃을 직관적으로 구축할 수 있는 많은 기능이 있다.</p>
<p><code>Flex</code>는 한 방향 레이아웃 시스템 (1차원)
<code>Grid</code>는 두 방향(가로-세로) 레이아웃 시스템 (2차원) 
<br /><br /></p>
<h2 id="✅-그리드-레이아웃grid-layout이란">✅ 그리드 레이아웃(Grid Layout)이란?</h2>
<blockquote>
<p>그리드는 <strong>수평과 수직으로 이루어진 집합체</strong>로, 디자인 요소를 정렬할 수 있는 대상 패턴을 생성한다.</p>
</blockquote>
<p>그리드 레이아웃 디자인은 요소가 널뛰거나 너비가 바뀌지 않도록 디자인 생성에 도움을 주어 웹 사이트의 일관성을 높여준다.</p>
<p>CSS Grid는 예전부터 핵(Hack)으로 불린 다양한 레이아웃 대체 방식들을 해결하기 위해 만들어진 특별한 CSS 모듈이다.
<br /><br /></p>
<h2 id="✅-용어-정리">✅ 용어 정리</h2>
<ul>
<li><strong>그리드 컨테이너(Grid Container)</strong>: display: grid를 적용하는 Grid의 전체 영역</li>
<li><strong>그리드 아이템(Grid Item)</strong>: Grid 컨테이너의 자식 요소들</li>
<li><strong>그리드 트랙(Grid Track)</strong>: Grid의 행(Row) 또는 열(Column)</li>
<li><strong>그리드 셀(Grid Cell)</strong>: Grid의 한 칸</li>
<li><strong>그리드 라인(Grid Line)</strong>: Grid 셀을 구분하는 선</li>
<li><strong>그리드 번호(Grid Number)</strong>: Grid 라인의 각 번호</li>
<li><strong>그리드 갭(Grid Gap)</strong>: Grid 셀 사이의 간격</li>
<li><strong>그리드 영역(Grid Area)</strong>: 그리드 셀의 집합. Grid 라인으로 둘러싸인 사각형 영역</li>
</ul>
<p>Grid의 속성은 <code>컨테이너에 적용하는 속성</code>과 <code>아이템에 적용하는 속성</code>으로 나뉜다.
<br /><br /></p>
<h2 id="✅-그리드-컨테이너-속성">✅ 그리드 컨테이너 속성</h2>
<p>그리드 컨테이너(Grid Container)는 <code>display: grid;</code>를 적용하는, 아이템들을 감싸고 있는 전체 영역이다.
<br /></p>
<h3 id="display">display</h3>
<p>Grid Container(컨테이너)를 정의하는 속성.
그리드를 사용하기 위해 필수로 작성해야하는 속성이다. 정의된 컨테이너의 자식 요소들은 자동으로 Grid Items(아이템)로 정의된다.
<br /></p>
<ul>
<li>grid: Block 특성의 Grid Container를 정의</li>
<li>inline-grid: Inline 특성의 Grid Container를 정의</li>
</ul>
<pre><code class="language-css">.container {
  display: grid;
  display: inline-grid;
}</code></pre>
<br />

<h3 id="grid-template-rows와-grid-template-columns">grid-template-rows와 grid-template-columns</h3>
<p>컨테이너에 Grid 트랙의 크기들을 지정해주는 속성</p>
<p><code>grid-template-rows</code>는 명시적 행(rows, Track)의 크기를 정의한다. 
<code>grid-template-columns</code> 명시적 열(columns, Track)의 크기를 정의한다.</p>
<p>여러가지 단위를 사용할 수 있고 섞어서 쓸 수도 있는데, 라인(Line)의 이름도 정의할 수 있고, fr(fraction, 공간 비율) 단위를 사용과 repeat() 함수를 사용할 수 있다.</p>
<pre><code class="language-css">.container {
    /* 행 */
    grid-template-rows: 200px 200px 500px;
    /* grid-template-rows: 1fr 1fr 1fr */
    /* grid-template-rows: repeat(3, 1fr) */
    /* grid-template-rows: 200px 1fr */
    /* grid-template-rows: 100px 200px auto */

    /* 열 */
    grid-template-columns: 200px 200px 500px;
    /* grid-template-columns: 1fr 1fr 1fr */
    /* grid-template-columns: repeat(3, 1fr) */
    /* grid-template-columns: 200px 1fr */
    /* grid-template-columns: 100px 200px auto */
}</code></pre>
<p>여기서 <code>fr</code>은 fraction, 비율대로 트랙의 크기를 나눈다.
e.g.) 1fr 1fr 1fr -&gt; 1:1:1</p>
<p>섞어서 사용 할 수도 있다.
e.g.) 100px 2fr 1fr -&gt; 100px 고정 값. 그리고 나머지 2:1 비율</p>
<h4 id="·-repeat-함수">· repeat 함수</h4>
<p>🌠 <strong>그리고 또 자주 사용하는 <code>repeat</code> 함수</strong>
<strong>repeat는 반복되는 값을 자동으로 처리할 수 있다.</strong>
 repeat(반복횟수, 반복값);</p>
<pre><code class="language-html">e.g)
repeat(5, 1fr) -&gt; 1fr 1fr 1fr 1fr 1fr
repeat(3, 1fr 4fr 2fr); 이런 식의 패턴도 가능하다.</code></pre>
<h4 id="·-minmax-함수">· minmax 함수</h4>
<p>최솟값과 최댓값을 지정할 수 있는 함수다.</p>
<pre><code class="language-html">e.g.)
repeat(3, minmax(100px, auto)) -&gt; 
최소한 100px, 최대는 자동으로(auto) 늘어나게</code></pre>
<h4 id="·-auto-fill과-auto-fit">· auto-fill과 auto-fit</h4>
<p>auto-fill과 auto-fit은 열과 행의 개수를 미리 정하지 않고 설정된 너비가 허용하는 한 최대한 셀을 채운다</p>
<pre><code class="language-html">e.g.) 
repeat(auto-fill, minmax(20%, auto))
auto-fill의 크기를 20%로 설정했으므로,
1개의 row에는 5개의 셀이 들어가는데 셀의 개수가 5개 미만이면 공간이 남게된다. </code></pre>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/3549f2f3-0340-42ba-b611-6762e99c8fbd/image.png" /></p>
<pre><code class="language-html">auto-fill과 auto-fit의 차이는,
auto-fill 대신 auto-fit을 사용하면 남는 공간을 채운다.</code></pre>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/9deaef01-e7fc-46ad-b5ba-bb14da1581bb/image.png" /></p>
<h4 id="·-이름-정의">· 이름 정의</h4>
<ul>
<li>각 라인의 이름 정의: [first] 100px [second] 200px [third];</li>
<li>라인에 중복된 이름 지정: [row1-start] 100px [row1-end row2-start] 200px [row2-end];<pre><code class="language-css">.container {
display: grid;
grid-template-rows: 1행크기 2행크기 ...;
grid-template-rows: [선이름] 1행크기 [선이름] 2행크기 [선이름] ...;
}</code></pre>
🌠 각 행과 열의 갯수대로 숫자 라인 이름이 자동으로 지정되어 있어서 꼭 필요한 경우가 아니면 라인 이름을 정의할 필요가 없다. (이런 방법도 있다 정도로만..)<br />

</li>
</ul>
<h3 id="row-gap-column-gap-gap">row-gap, column-gap, gap</h3>
<p>그리드 셀 사이의 간격을 설정한다.</p>
<pre><code class="language-css">.container {
    /* row-gap: 20px; column-gap: 20px; */
    gap: 20px;
    /* row-gap: 10px; column-gap: 20px; */
    gap: 10px 20px;
    /* row의 간격을 10px로 */
    row-gap: 10px;
    /* column의 간격을 20px로 */
    column-gap: 20px;
}</code></pre>
<br />

<h3 id="grid-auto-rows와-grid-auto-columns">grid-auto-rows와 grid-auto-columns</h3>
<p>통제를 벗어난 위치에 있는 트랙의 크기를 지정하는 속성.
그리드 형태를 <code>-auto-</code>자동으로 정의한다.</p>
<pre><code class="language-css">e.g.)
.container {
    grid-template-rows: repeat(3, minmax(100px, auto));
}
- 셀마다 최소 100px의 높이를 확보
- 컨텐츠가 높이 100px을 넘어가면 알아서 자동으로 늘어나도록(auto)
- row 3개 반복</code></pre>
<p>row 개수를 미리 알 수 없는 경우라면?</p>
<pre><code class="language-css">e.g.)
.container {
    grid-auto-rows: minmax(100px, auto);
}</code></pre>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/6174067c-0cd2-4124-bb76-eaa478ed7356/image.png" /></p>
<p>굳이 횟수를 지정해서 반복할 필요없이 알아서 처리
<br /></p>
<h3 id="grid-template-areas">grid-template-areas</h3>
<p>각 영역(Grid Area)에 이름을 붙이고, 그 이름을 이용해서 배치하는 방법</p>
<p>각자 차지하는 셀의 개수만큼 해당 위치에 이름을 써주면 된다.
빈칸은 마침표 또는 none을 사용하면 되고, 마침표의 개수는 여러개를 써도 상관 없다.</p>
<pre><code class="language-css">.container {
    grid-template-areas:
        &quot;header header header&quot;
        &quot;   a    main    b   &quot;
        &quot;   .     .      .   &quot;
        &quot;footer footer footer&quot;;
}</code></pre>
<p>각 영역의 이름 매칭은 <code>grid-area</code> 속성으로 이름을 지정해준다.</p>
<pre><code class="language-css">.header { grid-area: header; }
.sidebar-a { grid-area: a; }
.main-content { grid-area: main; }
.sidebar-b { grid-area: b; }
.footer { grid-area: footer; }
/* 이름 값에 따옴표가 없는 것에 주의 */</code></pre>
<br />

<h3 id="grid-auto-flow">grid-auto-flow</h3>
<p>아이템이 자동 배치되는 흐름을 결정하는 속성이다.</p>
<pre><code class="language-css">.container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(25%, auto));
    grid-template-rows: repeat(5, minmax(50px,auto));
    grid-auto-flow: dense;
}
item:nth-child(2) { grid-column: auto / span 3; }
item:nth-child(5) { grid-column: auto / span 3; }
item:nth-child(7) { grid-column: auto / span 2; }</code></pre>
<br />

<h3 id="align-items">align-items</h3>
<p>아이템들을 세로(column축) 방향으로 정렬한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/976e8138-8a2e-460d-9360-a7ad19330e41/image.png" /></p>
<ul>
<li>normal: stretch와 같다.</li>
<li>start: 시작점(위쪽) 정렬</li>
<li>center: 수직 가운데 정렬</li>
<li>end: 끝점(아래쪽) 정렬</li>
<li>stretch:열 축을 채우기 위해 그리드 아이템을 늘림<pre><code class="language-css">.container {
  align-items: stretch;
  /* align-items: start; */
  /* align-items: center; */
  /* align-items: end; */
}</code></pre>
<br />

</li>
</ul>
<h3 id="justify-items">justify-items</h3>
<p>아이템들을 가로(row축) 방향으로 정렬한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/ece1bd23-fa92-4a49-bd58-0def2563ab05/image.png" /></p>
<ul>
<li>normal: stretch와 같다.</li>
<li>start: 시작점(왼쪽) 정렬</li>
<li>center: 수평 가운데 정렬</li>
<li>end: 끝점(오른쪽) 정렬</li>
<li>stretch:행 축을 채우기 위해 그리드 아이템을 늘림<pre><code class="language-css">.container {
  justify-items: stretch;
  /* justify-items: start; */
  /* justify-items: center; */
  /* justify-items: end; */
}</code></pre>
<br />

</li>
</ul>
<h3 id="place-items">place-items</h3>
<p><code>align-items</code>와 <code>justify-items</code>를 같이 쓸 수 있는 단축 속성</p>
<p>🌠 <strong>Edge(IE) 브라우저에서 지원하지 않는 속성</strong></p>
<pre><code class="language-css">.container {
    /* align-items, justify-items의 순서로 작성 */
    place-items: center start;
}</code></pre>
<br />

<h3 id="align-content">align-content</h3>
<p>Grid 아이템들의 높이를 모두 합한 값이 Grid 컨테이너의 높이보다 작을 때, Grid 아이템들을 통째로 정렬</p>
<ul>
<li>normal: stretch와 같다.</li>
<li>start: 시작점(위쪽) 정렬</li>
<li>center: 수직 가운데 정렬</li>
<li>end: 끝점(아래쪽) 정렬</li>
<li>space-around: 각 행 위아래에 여백을 고르게 정렬</li>
<li>space-between: 첫 행은 시작점에, 끝 행은 끝점에 정렬되고 나머지 여백으로 고르게 정렬    </li>
<li>space-evenly: 모든 여백을 고르게 정렬</li>
<li>stretch: 열 축을 채우기 위해 그리드 콘텐츠를 늘림<pre><code class="language-css">.container {
  align-content: stretch;
  /* align-content: start; */
  /* align-content: center; */
  /* align-content: end; */
  /* align-content: space-between; */
  /* align-content: space-around; */
  /* align-content: space-evenly; */
}</code></pre>
<br />

</li>
</ul>
<h3 id="justify-content">justify-content</h3>
<p>Grid 아이템들의 너비를 모두 합한 값이 Grid 컨테이너의 너비보다 작을 때 Grid 아이템들을 통째로 정렬</p>
<ul>
<li>normal: stretch와 같다.</li>
<li>start: 시작점(왼쪽) 정렬</li>
<li>center: 수평 가운데 정렬</li>
<li>end: 끝점(오른쪽) 정렬</li>
<li>space-around: 각 열 좌우에 여백을 고르게 정렬</li>
<li>space-between: 첫 열은 시작점에, 끝 열은 끝점에 정렬되고 나머지 여백으로 고르게 정렬</li>
<li>space-evenly: 모든 여백을 고르게 정렬</li>
<li>stretch: 행 축을 채우기 위해 그리드 콘텐츠를 늘림<pre><code class="language-css">.container {
  justify-content: stretch;
  /* justify-content: start; */
  /* justify-content: center; */
  /* justify-content: end; */
  /* justify-content: space-between; */
  /* justify-content: space-around; */
  /* justify-content: space-evenly; */
}</code></pre>
<br />

</li>
</ul>
<h3 id="place-content">place-content</h3>
<p><code>align-content</code>와 <code>justify-content</code>를 같이 쓸 수 있는 단축 속성</p>
<p>🌠 <strong>Edge(IE) 브라우저에서 지원하지 않는 속성</strong></p>
<pre><code class="language-css">.container {
    /* align-content, justify-content의 순서로 작성 */
    place-content: space-between center;
}</code></pre>
<p><br /><br /></p>
<h2 id="✅-그리드-아이템-속성">✅ 그리드 아이템 속성</h2>
<p>정의된 컨테이너의 자식 요소들은 자동으로 Grid Items(아이템)로 정의된다.
<br /></p>
<h3 id="grid-column-start-grid-column-end-grid-column-grid-row-start-grid-row-end-grid-row">grid-column-start, grid-column-end, grid-column, grid-row-start, grid-row-end, grid-row</h3>
<p>Grid 아이템에 적용하는 속성으로, 각 셀의 영역을 지정한다.
아래 이미지에 Grid 라인 번호가 매겨져 있는데, 번호를 이용해 행과 열의 범위를 결정한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/dc4d9282-c791-4446-b8aa-e4dac508634d/image.png" />
위 이미지를 코드로 적용 시, 아래와 같다.</p>
<pre><code class="language-css">.item:nth-child(1) {
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start: 1;
    grid-row-end: 2;

    grid-column: 1 / 3;
    grid-row: 1 / 2;
}</code></pre>
<p>이렇게 설정하면 영역은 아래와 같다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/fb112af3-93c2-49d9-9cfe-7cab93eb61ea/image.png" />
시작번호 / 끝번호를 지정하는 방법 외에 몇 개의 셀을 차지하게 할 것인지를 지정해줄 수도 있다.</p>
<pre><code class="language-css">.item:nth-child(1) {
    /* 1번 라인에서 2칸 */
    grid-column: 1 / span 2;
    /* 1번 라인에서 3칸 */
    grid-row: 1 / span 3;
}</code></pre>
<p>통제받지 않는 column들도 만들 수 있다.</p>
<pre><code class="language-css">.container {
    grid-template-columns: 50px;
    grid-auto-columns: 1fr 2fr;
}
.item:nth-child(1) { grid-column: 2; }
.item:nth-child(2) { grid-column: 3; }
.item:nth-child(3) { grid-column: 4; }
.item:nth-child(4) { grid-column: 5; }
.item:nth-child(5) { grid-column: 6; }
.item:nth-child(6) { grid-column: 7; }
/* end를 생략하면 그냥 한 칸임 */</code></pre>
<br />

<h3 id="align-self">align-self</h3>
<p>해당 아이템을 세로(column축) 방향으로 정렬
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/5b4e491a-969d-425a-9c4f-830b10b16dc4/image.png" /></p>
<pre><code class="language-css">.item {
    align-self: stretch;
    /* align-self: start; */
    /* align-self: center; */
    /* align-self: end; */
}</code></pre>
<br />

<h3 id="justify-self">justify-self</h3>
<p>해당 아이템을 가로(row축) 방향으로 정렬
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/4cc2411f-405a-4783-8f28-a43f4f8189e9/image.png" /></p>
<pre><code class="language-css">.item {
    justify-self: stretch;
    /* justify-self: start; */
    /* justify-self: center; */
    /* justify-self: end; */
}</code></pre>
<br />

<h3 id="place-self">place-self</h3>
<p><code>align-self</code>와 <code>justify-self</code>를 같이 쓸 수 있는 단축 속성</p>
<p>🌠 <strong>Edge(IE) 브라우저에서 지원하지 않는 속성</strong></p>
<pre><code class="language-css">.container {
    /* align-self, justify-self의 순서로 작성 */
    place-self: start center;
}</code></pre>
<br />

<h3 id="order">order</h3>
<p>각 아이템들의 배치 순서를 결정하는 속성
숫자값이 들어가며, 작은 숫자일 수록 먼저 배치</p>
<p>🌠 <strong>시각적 순서일 뿐, HTML 자체의 구조를 바꾸는 것은 아니므로 접근성 측면에서 사용에 주의</strong></p>
<pre><code class="language-css">a &gt; b &gt; c

.item:nth-child(1) { order: 3; } /* A */
.item:nth-child(2) { order: 1; } /* B */
.item:nth-child(3) { order: 2; } /* C */

결과: b &gt; c &gt; a</code></pre>
<br />

<hr />
<h2 id="참고자료">참고자료</h2>
<p><a href="https://developer.mozilla.org/ko/docs/Learn_web_development/Core/CSS_layout/Grids">https://developer.mozilla.org/ko/docs/Learn_web_development/Core/CSS_layout/Grids</a>
<a href="https://www.heropy.dev/p/c6ROLZ">https://www.heropy.dev/p/c6ROLZ</a>
<a href="https://studiomeal.com/archives/533">https://studiomeal.com/archives/533</a></p>