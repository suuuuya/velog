<h2 id="week15-위클리-페이퍼">week15 위클리 페이퍼</h2>
<ul>
<li>CORS 에러에 대해 설명하고, 어떻게 해결하면 될지 설명해 주세요.</li>
<li>SEO가 무엇인지 설명하고, 개선을 위해 어떤 작업을 할 수 있을지 설명해 주세요.<br />

</li>
</ul>
<hr />
<br />

<h3 id="💬-cors-에러에-대해-설명하고-어떻게-해결하면-될지-설명해-주세요">💬 CORS 에러에 대해 설명하고, 어떻게 해결하면 될지 설명해 주세요.</h3>
<h4 id="cors">CORS</h4>
<blockquote>
<p>Cross-Origin Resource Sharing(교차 출처 리소스 공유)의 약자. 
출처가 다른 자원들을 공유한다는 뜻으로, <strong>한 출처에 있는 자원에서 다른 출처에 있는 자원에 접근하도록 하는 개념</strong>입니다.</p>
</blockquote>
<p> 기본적으로 브라우저에서는 보안을 위해 같은 출처에서만 자원 공유를 허용하는데(SOP),
 <u>CORS 오류는 다른 출처로 리소스를 요청했을 때 발생</u>합니다.
 <br /></p>
<p><strong>출처(origin)란?</strong>
 출처는 세 가지 요소(프로토콜 + 도메인 + 포트)로 구성됩니다.</p>
  <br />

<h4 id="cors-에러">CORS 에러</h4>
<p>필요한 설정을 하지 않은 채 서로 다른 출처에서 리소스를 공유하려고 하면 브라우저에서 동일 출처 정책에 따라 허용되지 않은 교차 출처 리소스 공유에 대해 CORS 에러가 발생할 수 있습니다.</p>
<ul>
<li>웹 페이지가 <code>https://my-frontend.com</code>에서 실행 중인데</li>
<li>API 요청을 <code>https://api.my-backend.com</code>으로 보내려고 하면</li>
<li>브라우저는 이를 교차 출처 요청으로 인식</li>
<li>서버가 이를 허용하지 않으면 브라우저는 CORS 에러를 발생</li>
</ul>
<br />

<h4 id="해결-방법">해결 방법</h4>
<ul>
<li>기본적인 방법은 서버에서 <code>Access-Control-Allow-Origin</code> 헤더를 셋팅을 하는 것</li>
<li>프론트에서 proxy 서버로 해결</li>
</ul>
<br />


<p><a href="https://ramoo1101.tistory.com/60">참고 블로그 | CORS 에러란? 해결법은?</a>
<a href="https://aws.amazon.com/ko/what-is/cross-origin-resource-sharing/">참고 자료 | AWS</a>
<a href="https://www.codeit.kr/tutorials/95/CORS%EB%9E%80%3F">참고 자료 | 코드잇</a></p>
<br />

<hr />
<br />

<h3 id="💬-seo가-무엇인지-설명하고-개선을-위해-어떤-작업을-할-수-있을지-설명해-주세요">💬 SEO가 무엇인지 설명하고, 개선을 위해 어떤 작업을 할 수 있을지 설명해 주세요.</h3>
<h4 id="seo">SEO</h4>
<blockquote>
<p>SEO는 검색 엔진 최적화(Search Engine Optimization)의 약자</p>
</blockquote>
<p>웹사이트나 웹페이지를 검색 엔진에서 더 잘 찾을 수 있도록 최적화하는 과정을 말합니다.</p>
<br />

<h4 id="seo가-중요한-이유">SEO가 중요한 이유</h4>
<p>검색 엔진에서 높은 순위(상위 랭킹)를 차지하는 것이 더 많은 트래픽을 유도하고, 브랜드 인지도를 향상시키는 가장 효과적인 방법 중 하나이기 때문입니다. </p>
<br />

<h4 id="검색-엔진-동작-원리">검색 엔진 동작 원리</h4>
<p>SEO를 효과적으로 수행하기 위해서는 검색 엔진이 어떻게 작동하는지 이해하는 것이 중요합니다.
구글이나 네이버와 같은 검색 엔진은 웹을 끊임없이 돌아다니며 정보를 수집하고 정리하는데, </p>
<p>이 과정은 크게 세 단계로 나뉩니다.</p>
<ul>
<li><strong>크롤링</strong>
로봇이 웹을 탐색하며 웹페이지 내용을 수집합니다. 
링크를 따라 새 페이지를 발견하고 기존 페이지의 변경 사항을 확인합니다.</li>
<li><strong>인덱싱</strong>
크롤링으로 모은 정보를 분석하고 데이터베이스에 저장합니다. 
이 과정에서 웹페이지의 내용, 이미지, 비디오 등을 분류합니다.</li>
<li><strong>랭킹</strong>
사용자가 검색어를 입력하면 검색 엔진은 인덱싱된 정보 중 가장 관련성 높고 유용한 결과를 찾아 순위를 매깁니다.
이 과정에서 알고리즘을 고려해 가장 적절한 결과를 상위에 노출시킵니다.</li>
</ul>
<br />

<h4 id="seo-개선">SEO 개선</h4>
<p>SEO는 크게 세 가지 유형으로 나눌 수 있는데요.</p>
<ul>
<li>웹사이트의 기술적 측면을 최적화하는 <code>기술적 SEO</code></li>
<li>웹페이지 내부의 콘텐츠와 소스 코드를 최적화하는 <code>온페이지 SEO</code></li>
<li>웹사이트 외부 요소를 최적화하는 <code>오프페이지 SEO</code></li>
</ul>
<br />
SEO를 개선하기 위한 작업에 대한 자세한 내용은 아래 블로그에 정리했습니다.

<p><a href="https://velog.io/@iamsuuya/%EB%8D%B0%EC%9D%BC%EB%A6%AC-%ED%8C%80%EB%AF%B8%EC%85%98-Next.js-Middleware-SEO">[Next.js] SEO를 개선하기 위해 Next.js에서 사용할 수 있는 방법</a>
<a href="https://velog.io/@iamsuuya/HTML5-%EB%A9%94%ED%83%80%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0">[HTML5] 메타데이터(Metadata) 이해하기</a></p>