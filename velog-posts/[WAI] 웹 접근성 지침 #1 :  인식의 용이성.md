<h2 id="✅-인식의-용이성">✅ 인식의 용이성</h2>
<h3 id="1-적절한-대체-텍스트-제공">1. 적절한 대체 텍스트 제공</h3>
<p>텍스트 아닌 콘텐츠는 그 의미나 용도를 인식할 수 있도록 대체 텍스트를 제공해야 한다.</p>
<h4 id="alt-제공">alt 제공</h4>
<p><code>&lt;img&gt;</code>, <code>&lt;input type="image"&gt;</code>, <code>&lt;area&gt;</code> 의 <code>alt</code>에는 적절한 대체 텍스트를 제공한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/96236447-a003-447f-af48-933db6803fff/image.png" /></p>
<pre><code class="language-HTML">&lt;!-- 소스 코드 --&gt;
&lt;img src=&quot;banner.jpg&quot; alt=&quot;&quot;&gt;

&lt;!-- 해결 방안 --&gt;
&lt;img src=&quot;banner.jpg&quot; alt=&quot;방송사 유일 무료 OTT앱 KBS+ 지금 다운로드 하세요! 앱 소개 페이지로 이동&quot;&gt;

&lt;!-- 그러나, 이미지와 텍스트 의미가 중복되는 경우에 alt는 그대로 비워둔다. --&gt;
&lt;figure&gt;
  &lt;img src=&quot;banner.jpg&quot;&gt; (X) 접근성에 맞지 않음
  &lt;img src=&quot;banner.jpg&quot; alt=&quot;&quot;&gt; (o) alt 속성 빈 값으로 두기
&lt;/figure&gt;
&lt;figcaption&gt;구글 애널리틱스 4 소개&lt;/figcaption&gt;</code></pre>
<br />

<h4 id="·-ir-기법">· IR 기법</h4>
<p>특수문자, 기호 포함, 조직도, 차트 등 복잡한 콘텐츠의 경우 숨김 처리로 대체 텍스트를 제공한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/b0c9ffeb-e34c-4c96-88f7-3d4454870d6c/image.png" /></p>
<pre><code class="language-HTML">&lt;!-- 소스 코드 --&gt;
&lt;button type=&quot;button&quot;&gt;&lt;/button&gt;
&lt;a href=”#” class=”menu”&gt;&lt;/a&gt;
&lt;button&gt;&lt;/button&gt;

&lt;!-- 해결 방안 --&gt;
&lt;button type=&quot;button&quot; aria-label=&quot;이미지 삭제&quot;&gt;&lt;/button&gt;
&lt;button type=&quot;button&quot;&gt;&lt;span class=”blind”&gt;이미지 삭제&lt;/span&gt;&lt;/button&gt;
&lt;a href=”#” class=”menu”&gt;&lt;span class=”blind”&gt;메뉴&lt;/span&gt;&lt;/a&gt;
&lt;button&gt;&lt;span class=”blind”&gt;이미지형&lt;/span&gt;&lt;/button&gt;</code></pre>
<br />

<h4 id="·-의미-없는-이미지">· 의미 없는 이미지</h4>
<p>장식 또는 꾸밈 목적 등의 의미 없는 이미지는 대체 텍스트를 제공하지 않는다.</p>
<pre><code class="language-HTML">&lt;!-- 소스 코드 --&gt;
&lt;img src=”border.jpg” alt=”구분선” /&gt;

&lt;!-- 해결 방안 --&gt;
&lt;img src=”border.jpg” alt=”” /&gt;</code></pre>
<br />

<h4 id="·-이모티콘-이미지">· 이모티콘 이미지</h4>
<p>이모티콘의 의미를 파악할 수 있도록 적절한 대체 텍스트를 제공한다.</p>
<pre><code class="language-HTML">&lt;!-- 소스 코드 --&gt;
&lt;img src=”emoticon.png” alt=”이모티콘” /&gt;

&lt;!-- 해결 방안 --&gt;
&lt;img src=”emoticon.png” alt=”웃는 얼굴” /&gt;</code></pre>
<br />

<h4 id="·-qr코드-이미지">· QR코드 이미지</h4>
<p>해당 링크를 알 수 있도록 대체 텍스트를 제공한다.</p>
<pre><code class="language-HTML">&lt;!-- 소스 코드 --&gt;
&lt;img src=”qr_code.png” alt=”QR코드” /&gt;

&lt;!-- 해결 방안 --&gt;
&lt;img src=”qr_code.png” alt=”QR코드 네이버 바로가기 http:\\www.naver.com” /&gt;</code></pre>
<br />

<h4 id="·-thumbnail-이미지">· Thumbnail 이미지</h4>
<p>이미지에 해당하는 텍스트를 a태그로 묶어서 중복 제공되지 않도록 제공한다.
묶을 수 없는 경우에는 중복되더라도 이미지에 대한 대체 텍스트를 제공한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/fbd6d171-186a-4b31-b867-05891f79f598/image.png" /></p>
<pre><code class="language-HTML">&lt;!-- 소스 코드 --&gt;
&lt;a href=”#”&gt;
  &lt;figure&gt;&lt;img src=”thumb-1.jpg” alt=”썸내일” /&gt;&lt;/figure&gt;
  &lt;figcaption&gt;
      유키 구라모토 (With. 김연아) - Lake Louise, Warm Affection / 최유리 - 숲, 잠수 / KISS OF LIFE (키스오브라이프) - Sticky + Igloo (Band VER.), Lips Hips Kiss (Band VER.)
  &lt;/figcaption&gt;
  ...
&lt;/a&gt;

&lt;!-- 해결 방안 --&gt;
&lt;a href=”#”&gt;
  &lt;figure&gt;&lt;img src=”thumb-1.jpg” alt=”” /&gt;&lt;/figure&gt;
  &lt;figcaption&gt;
      유키 구라모토 (With. 김연아) - Lake Louise, Warm Affection / 최유리 - 숲, 잠수 / KISS OF LIFE (키스오브라이프) - Sticky + Igloo (Band VER.), Lips Hips Kiss (Band VER.)
  &lt;/figcaption&gt;
  ...
&lt;/a&gt;</code></pre>
<br />

<h4 id="·-captcha-이미지">· Captcha 이미지</h4>
<p>음성으로 들을 수 있도록 청각적 캡차를 같이 제공한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/122bf93b-f3bd-4bd0-9d67-ba6907b63ffe/image.png" /></p>
<pre><code class="language-HTML">&lt;!-- 소스 코드 --&gt;
&lt;img src=”text.jpg” alt=”146N3” /&gt;

&lt;!-- 해결 방안 --&gt;
&lt;img src=”text.jpg” alt=”보안문자” /&gt;
&lt;button&gt;음성으로 듣기&lt;/button&gt;</code></pre>
<br />

<h4 id="·-사용자가-업로드하는-이미지">· 사용자가 업로드하는 이미지</h4>
<p>사용자가 직접 대체 텍스트를 제공할 수 있도록 안내하고 툴을 제공한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/f5952519-385e-4324-aca3-7746695da528/image.png" /> 
<br /></p>
<h3 id="2-자막-제공">2. 자막 제공</h3>
<p>멀티미디어 콘텐츠에는 자막, 대본 또는 수화를 제공해야 한다.</p>
<h4 id="·-멀티미디어">· 멀티미디어</h4>
<p>자막 또는 대본 또는 수화를 제공한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/ebf1cf30-8961-4bfd-993a-a84de25829ed/image.png" /></p>
<h4 id="·-사용자가-업로드하는-멀티미디어">· 사용자가 업로드하는 멀티미디어</h4>
<p>대체 콘텐츠를 제공할 수 있도록 안내하고 툴을 제공한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/ca1abadf-53af-4b10-b05a-ef5099ca2c77/image.png" /></p>
<h4 id="·-음성이-나오지-않는-멀티미디어">· 음성이 나오지 않는 멀티미디어</h4>
<p>청각적으로도 인식이 가능하도록 원고 등의 대체 콘텐츠를 제공한다.
<br /><br /><br /></p>
<h3 id="3-색에-무관한-콘텐츠-인식">3. 색에 무관한 콘텐츠 인식</h3>
<p>콘텐츠는 색에 관계없이 인식될 수 있어야 한다.</p>
<h4 id="차트">차트</h4>
<p>색이 아닌 패턴, 굵기, 모양, 테두리 등의 다양한 방법으로 구분할 수 있도록 제공한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/029fb870-8439-4972-bbdb-c304515c5761/image.png" /></p>
<h4 id="슬라이드-버튼-선택-여부">슬라이드 버튼 선택 여부</h4>
<p>색이 아닌 패턴, 굵기, 모양, 테두리 등의 다양한 방법으로 구분할 수 있도록 제공한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/6c0be26e-95e3-42b7-b393-b48874dcb988/image.png" /></p>
<h4 id="페이지내이션">페이지내이션</h4>
<p>색이 아닌 패턴, 굵기, 모양, 테두리 등의 다양한 방법으로 구분할 수 있도록 제공한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/56b6d4d4-5286-44e4-b6da-60b11244a5b0/image.png" /></p>
<h4 id="슬라이드-버튼-선택-여부-1">슬라이드 버튼 선택 여부</h4>
<p>색이 아닌 패턴, 굵기, 모양, 테두리 등의 다양한 방법으로 구분할 수 있도록 제공한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/6a6664f3-d01e-4bfc-b560-85120ab0bd96/image.png" />
<br /></p>
<h3 id="4-명확한-지시-사항-제공">4. 명확한 지시 사항 제공</h3>
<p>지시 사항은 모양, 크기, 위치, 방향, 색, 소리 등에 관계없이 인식될 수 있어야 한다.</p>
<h4 id="·-모양으로만-정보-제공">· 모양으로만 정보 제공</h4>
<p>준수 사례
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/ebf41f25-42ce-4e44-a9cb-23f391f8e40c/image.png" /></p>
<h4 id="·-위치나-방향으로만-정보-제공">· 위치나 방향으로만 정보 제공</h4>
<p>오류 사례<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/c8640ecb-5928-41ca-ae21-caa29dcc412b/image.png" /></p>
<h4 id="·-크기로만-정보-제공">· 크기로만 정보 제공</h4>
<p>오류 사례
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/9f275be1-d814-43ae-8815-e0ddc329edae/image.png" /></p>
<h4 id="·-색으로만-정보-제공">· 색으로만 정보 제공</h4>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/0d55e328-5933-4398-a7c4-6927dde13716/image.png" />
<br /></p>
<h3 id="5-텍스트-콘텐츠의-명도-대비">5. 텍스트 콘텐츠의 명도 대비</h3>
<p>텍스트 콘텐츠와 배경 간의 명도 대비는 4.5 대 1 이상이어야 한다.</p>
<h4 id="·-텍스트">· 텍스트</h4>
<p>텍스트 콘텐츠와 배경 간의 명도 대비가 4.5 대 1 이상이 되도록 제공한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/e1cf14d4-2732-44bd-a485-1f51bbeddaff/image.png" /></p>
<h4 id="·-이미지-내부-텍스트">· 이미지 내부 텍스트</h4>
<p>이미지 내부 텍스트 콘텐츠와 배경 간의 명도 대비가 4.5 대 1 이상이 되도록 제공한다.
(텍스트에 그림자 처리로 대비 보완 가능)
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/b28107c2-4a2d-4ab6-82e7-0baf71c067fc/image.png" /></p>
<h4 id="·-의미-있는-이미지">· 의미 있는 이미지</h4>
<p>이미지(아이콘 등)와 배경 간의 명도 대비가 4.5 대 1 이상이 되도록 제공한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/3c781d2e-7401-437e-8126-2ea7971470ec/image.png" />
<br /></p>
<h3 id="6-자동-재생-금지">6. 자동 재생 금지</h3>
<p>자동으로 소리가 재생되지 않아야 한다.</p>
<h4 id="·-페이지-진입-시-자동-재생되는-3초-이상의-배경음-콘텐츠동영상-포함">· 페이지 진입 시 자동 재생되는 3초 이상의 배경음 콘텐츠(동영상 포함)</h4>
<p>자동 재생음을 제공하지 않도록 한다.
<br /></p>
<h4 id="·-불가피하게-제공-해야-하는-경우">· 불가피하게 제공 해야 하는 경우</h4>
<p>3초 내 정지하거나 ESC 키 선택 시 정지하거나 소스 상 가장 먼저 위치해 정지 기능 실행 가능하도록 제공한다.
<br /><br /></p>
<h3 id="7-콘텐츠-간의-구분">7. 콘텐츠 간의 구분</h3>
<p>이웃한 콘텐츠는 구별될 수 있어야 한다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/0a19759a-9ad5-42cf-b877-41698a317aca/image.png" /></p>
<ul>
<li>테두리를 이용하여 구분</li>
<li>콘텐츠 사이에 시각적인 구분선을 삽입하여 구분</li>
<li>서로 다른 무늬를 이용하여 구분</li>
<li>콘텐츠 배경색 간의 명도대비(채도)를 달리하여 구분</li>
<li>줄 간격 및 글자 간격을 조절하여 구분</li>
<li>기타 콘텐츠를 시각적으로 구분할 수 있는 방법을 통해 구분<br />

</li>
</ul>
<hr />
<h2 id="참고자료">참고자료</h2>
<p><a href="https://nuli.navercorp.com/">https://nuli.navercorp.com/</a>
<a href="https://www.kbs.co.kr/">https://www.kbs.co.kr/</a>
<a href="https://www.w3.org/WAI/">https://www.w3.org/WAI/</a></p>