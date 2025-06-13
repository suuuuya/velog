<p>웹사이트를 운영하면서 방문자는 얼마나 오는지, 어떤 콘텐츠가 인기가 있는지, 어디서 유입되는지 이런 궁금증을 데이터로 명확하게 분석해주는 도구가 있다.
<br /><br /></p>
<h2 id="구글-애널리틱스google-analytics란">구글 애널리틱스(Google Analytics)란?</h2>
<blockquote>
<p>Google에서 제공하는 <strong>웹사이트/앱 트래픽 분석 도구</strong></p>
</blockquote>
<p>GA를 활용하면 내 웹사이트에 방문하는 사람들의 행동을 추적하고, 실시간으로 수집된 데이터를 기반으로 다양한 분석과 활용이 가능하다. 이탈 지점, 인기 콘텐츠, 전환율을 방해하는 요소를 파악해 사이트를 개선하고, 분석을 통해 얻은 인사이트는 마케팅 광고의 전략 수립이나 퍼포먼스를 높이는 데에 활용할 수 있다.
<br /><br /></p>
<h2 id="✅-ga4-주요-기능">✅ GA4 주요 기능</h2>
<h3 id="·-웹과-앱-통합-분석">· 웹과 앱 통합 분석</h3>
<p>GA4의 가장 큰 특징 중 하나는 웹과 앱 트래픽을 하나의 속성에 담아 통합적으로 운영할 수 있다는 점이다. 사용자 행동을 데이터를 통합적으로 수집, 비교, 분석할 수 있다.</p>
<h3 id="·-이벤트-기반-데이터-모델">· 이벤트 기반 데이터 모델</h3>
<p>그리고 사용자의 모든 활동을 이벤트로 저장한다. 기존 UA(Universal Analytics, 2023.7.1 서비스 종료, <span style="color: #999;"><del><em>구글 애널리틱스 버전 3이라고 생각하면 이해하기 쉽다.</em></del></span>)의 페이지뷰, 이벤트, 소셜 등 여러 유형으로 구분되어있었던 복잡한 데이터 모델을 이벤트 기반 데이터로 처리하여 커스텀 이벤트 정의가 유연해졌다.</p>
<p><strong>페이지 조회, 스크롤 등 6가지 이벤트를 자동으로 수집하는 향상된 측정 기능을 지원한다.</strong>
<code>page_view (페이지 조회)</code>, <code>scroll (스크롤)</code>, <code>click (이탈 클릭)</code>, <code>view_search_results (사이트 검색)</code>, <code>video_start, video_progress, video_complete (동영상에 호응)</code>, <code>file_download (파일 다운로드)</code></p>
<h3 id="·-세션-정의-방식의-변화">· 세션 정의 방식의 변화</h3>
<p>GA에서는 기본적으로 30분 동안 활동이 없으면 세션이 종료된 것으로 정의하고 사용자가 다시 활동을 시작했을 때 새로운 ID를 발급한다. 이러한 세션<a href="https://api.velog.io/rss/@iamsuuya#fn-def-1" id="fn-1"><sup>[1]</sup></a> 수 집계 방식이 변경되었다.<br /></p>
<h3 id="·-bigquery-연동-무료-제공">· BigQuery 연동 무료 제공</h3>
<p>BigQuery<a href="https://api.velog.io/rss/@iamsuuya#fn-def-2" id="fn-2"><sup>[2]</sup></a> raw 데이터 내보내기 기능을 무료로 지원한다. 유료 버전 GA360에서 제공되던 BigQuery 연동을 GA4에서는 무료로 제공되면서 이벤트 단위의 데이터를 SQL이라는 언어를 이용해 직접 분석할 수 있다. 또한 <u>BigQuery에 다른 서비스 데이터를 저장하고 있다면 그 데이터들과 GA4에서 수집한 사용자 행동 데이터를 연결하여 분석</u>하는 것도 가능하다.</p>
<h3 id="·-탐색-분석-기능-무료-제공">· 탐색 분석 기능 무료 제공</h3>
<p>유료 버전인 GA360<a href="https://api.velog.io/rss/@iamsuuya#fn-def-3" id="fn-3"><sup>[3]</sup></a>에서만 제공되던 분석 허브 기능을 GA4의 탐색 탭에서 무료로 이용 가능하다. 탐색 분석 기능이 추가되어 탐색 분석 템플릿을 이용해 다양한 분석을 할 수 있다.
<br /><br /></p>
<h2 id="✅-ga4로-할-수-있는-주요-분석-항목">✅ GA4로 할 수 있는 주요 분석 항목</h2>
<ul>
<li>일일 방문자 수, 페이지 뷰, 이탈률 등 트래픽 분석</li>
<li>방문자의 유입 경로(검색엔진, SNS, 직접 방문 등) 확인</li>
<li>방문자의 접속 웹/모바일 및 브라우저 확인</li>
<li>방문자의 사용자 행동(클릭, 스크롤, 이벤트 등)까지 세부적으로 추적</li>
<li>페이지에 머무는 시간과 어떤 콘텐츠가 인기가 있는지 지표로 사용<br />

</li>
</ul>
<div style="font-size: 0.8em; border-top: 1px dashed #f1f1f1; padding: 20px 15px 10px;">
  <a href="https://api.velog.io/rss/@iamsuuya#fn-1" id="fn-def-1">[1]</a> 일정한 기간 내 웹사이트에서 발생한 사용자 상호작용의 집합<br />
  <a href="https://api.velog.io/rss/@iamsuuya#fn-2" id="fn-def-2">[2]</a> 구글의 클라우드 데이터베이스 서비스<br />
  <a href="https://api.velog.io/rss/@iamsuuya#fn-3" id="fn-def-3">[3]</a> 구글 애널리틱스의 유료 버전
</div>


<hr />
<h2 id="끝으로">끝으로</h2>
<p>데이터 분석은 사용자 경험을 이해하고 개선하는 데 꼭 필요한 과정이라고  생각하기 때문에 꾸준히 관심을 가지고 분석 역량을 조금씩 키워가보려 한다. 쉽진 않겠지만 유연한 분석 환경을 제공해줄 좋은 도구인건 분명하니까.. 🥲🤯</p>
<hr />
<h2 id="참고자료">참고자료</h2>
<p><a href="https://support.google.com/analytics/answer/10089681?hl=ko">https://support.google.com/analytics/answer/10089681?hl=ko</a>
<a href="https://analyticsmarketing.co.kr/digital-analytics/google-analytics-4/5692/">https://analyticsmarketing.co.kr/digital-analytics/google-analytics-4/5692/</a></p>