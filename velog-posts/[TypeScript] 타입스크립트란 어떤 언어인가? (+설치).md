<h2 id="typescript">TypeScript</h2>
<blockquote>
<p>자바스크립트에서 <strong>타입 관련 기능들을 추가</strong>한 언어</p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/ebf51835-ff78-47f5-ad1e-d8424d89dc77/image.png" /></p>
<h4 id="타입스크립트가-필요한-이유">타입스크립트가 필요한 이유</h4>
<p>자바스크립트는 동적 타입 언어로 유연하지만, 대규모 프로젝트에서는 오류 발생 가능성이 높아지기도 한다. 타입스크립트는 이러한 자바스크립트의 단점을 보완하기 위해 개발되었고</p>
<blockquote>
<p>자바스크립트에 정적 타입 문법을 추가하여 <strong>코드 작성 시 발생할 수 있는 오류를 미리 찾아내고 개발 생산성과 프로젝트 품질을 향상시키는 데 중점</strong>을 둔다. </p>
</blockquote>
<br />

<hr />
<br />


<h2 id="자바스크립트의-단점">자바스크립트의 단점</h2>
<h4 id="자바스크립트의-한계점">자바스크립트의 한계점</h4>
<p>자바스크립트는 변수의 타입을 런타임에 결정하는 <strong>동적 타입 언어</strong>이다. 
이로 인해 타입 관련 오류가 컴파일이 아닌 실행 시점에 발견될 수 있어, 개발자가 모든 경우의 타입을 정확하게 관리해야 하는 어려움이 발생한다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/cbe45cda-da06-4909-8e87-ff84d6473454/image.png" /></p>
<br />

<hr />
<br />

<h2 id="타입스크립트는-이-한계점을-어떻게-극복하는가">타입스크립트는 이 한계점을 어떻게 극복하는가?</h2>
<h4 id="타입스크립트가-다른-언어-대비-갖는-차별점">타입스크립트가 다른 언어 대비 갖는 차별점</h4>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/4007c009-0046-47b8-9d49-c2f67e6d437a/image.png" /></p>
<p>자바스크립트의 동적 타입 시스템과 자바의 정적 타입 시스템을 혼합한 것 같은 타입 시스템을 사용한다.
정적 타입 시스템이 갖는 안정성을 채택하면서도 동시에 일일이 모든 변수의 타입을 선언해야 했던 불편함을 동시에 해결하는 유연함까지 확보한 그런 차별점을 가지고 있다.</p>
<br />

<hr />
<br />

<h2 id="설치">설치</h2>
<h4 id="typesnode-패키지-설치">types/node 패키지 설치</h4>
<pre><code class="language-bash">npm i @types/node</code></pre>
<h4 id="컴파일러-설치">컴파일러 설치</h4>
<pre><code class="language-bash">npm install -g typescript</code></pre>
<p><code>-g</code>는 패키지를 전역(global)으로 설치하겠다는 뜻
즉, 이 패키지를 현재 프로젝트 폴더만이 아니라, 컴퓨터 전체에서 사용할 수 있게 설치하겠다는 의미</p>
<br />

<h4 id="💡-mac에서-권한-오류-없이-typescript-설치하기">💡 Mac에서 권한 오류 없이 TypeScript 설치하기</h4>
<blockquote>
<p>sudo 없이 TypeScript 설치하는 방법</p>
</blockquote>
<pre><code class="language-bash"># nvm 설치
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

# 설치된 nvm 사용 가능하게 하기
export NVM_DIR=&quot;$HOME/.nvm&quot;
source &quot;$NVM_DIR/nvm.sh&quot;

# 최신 LTS 버전 Node 설치 및 사용
nvm install --lts
nvm use --lts

# 타입스크립트 전역 설치 (이제 sudo 필요 없음)
npm install -g typescript

# 설치 확인
tsc --version</code></pre>
<h4 id="tsconfigjson컴파일러-옵션-파일-생성">tsconfig.json(컴파일러 옵션) 파일 생성</h4>
<pre><code class="language-bash">tsc --init</code></pre>
<br />

<hr />
<br />

<h2 id="참고자료">참고자료</h2>
<ul>
<li>한 입 크기로 잘라먹는 타입스크립트</li>
</ul>