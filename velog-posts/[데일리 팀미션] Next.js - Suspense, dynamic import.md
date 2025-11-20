<h3 id="918목">9.18(목)</h3>
<ul>
<li>useSearchParams() 훅을 사용할 때 ‘Suspense 관련 에러’는 왜 발생하는건가요?</li>
<li>next/dynamic을 사용한 동적 import의 장점은 무엇이며, SSR 환경에서 주의해야 할 점은 무엇인가요?</li>
</ul>
<br />

<hr />
<br />

<h3 id="💬-usesearchparams-훅을-사용할-때-suspense-관련-에러는-왜-발생하는건가요">💬 useSearchParams() 훅을 사용할 때 ‘Suspense 관련 에러’는 왜 발생하는건가요?</h3>
<h4 id="usesearchparams">useSearchParams()</h4>
<blockquote>
<p><code>useSearchParams()</code>는 브라우저 URL 쿼리 파라미터(<code>?key=value</code>)를 읽고 조작할 수 있게 해주는 훅입니다.</p>
</blockquote>
<p>이 훅은 클라이언트 컴포넌트에서만 실행할 수 있는데, 서버 컴포넌트에서 사용하려고 하면 Suspense 관련 에러가 발생합니다.</p>
<h4 id="❓suspense">❓Suspense</h4>
<blockquote>
<p>Suspense는 서버 컴포넌트가 데이터를 로딩하는 동안 로딩 상태를 쉽게 처리할 수 있게 해주는 기능입니다.</p>
</blockquote>
<p>클라이언트 훅인 <code>useSearchParams()</code>를 서버 컴포넌트에서 사용하면 Suspense와 충돌이 일어나 에러가 발생하게 됩니다.</p>
<h4 id="해결-방법">해결 방법</h4>
<pre><code class="language-tsx">'use client'

import { useSearchParams } from 'next/navigation'</code></pre>
<p>컴포넌트 최상단에 <code>'use client'</code>를 넣어 클라이언트 컴포넌트로 만들면 Next.js가 해당 컴포넌트를 클라이언트에서 실행하도록 인식해서, <code>useSearchParams()</code> 훅이 정상적으로 동작하며 Suspense 관련 에러가 사라집니다. </p>
<pre><code class="language-tsx">import { Suspense } from 'react';
import { useSearchParams } from 'next/navigation';

function SearchParamsComponent() {
  ...

  export default function Page() {
    return (
      &lt;Suspense fallback={&lt;div&gt;로딩 중...&lt;/div&gt;}&gt;
        &lt;SearchParamsComponent /&gt;
      &lt;/Suspense&gt;
    );
  }
</code></pre>
<p>클라이언트 컴포넌트를 Suspense로 감싸서 로딩 상태를 관리할 수도 있습니다.
<br /></p>
<hr />
<br />

<h3 id="💬-nextdynamic을-사용한-동적-import의-장점은-무엇이며-ssr-환경에서-주의해야-할-점은-무엇인가요">💬 next/dynamic을 사용한 동적 import의 장점은 무엇이며, SSR 환경에서 주의해야 할 점은 무엇인가요?</h3>