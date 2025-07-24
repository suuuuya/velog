<h2 id="✅-빌드-명령어">✅ 빌드 명령어</h2>
<br />

<h3 id="🖥️-개발된-프로젝트-빌드하기">🖥️ 개발된 프로젝트 빌드하기</h3>
<pre><code class="language-bash">npm run build</code></pre>
<br />

<h3 id="🖥️-빌드한-것-로컬에서-실행하기">🖥️ 빌드한 것 로컬에서 실행하기</h3>
<blockquote>
<p>serve 프로그램을 다운 받고 build 폴더에서 서버가 실행된다.</p>
</blockquote>
<pre><code class="language-bash">npx serve build</code></pre>
<br />

<hr />
<br />

<h2 id="✅-웹-사이트-배포하기">✅ 웹 사이트 배포하기</h2>
<h3 id="aws-s3">AWS S3</h3>
<blockquote>
<p><a href="https://aws.amazon.com/ko/">aws.amazon.com</a></p>
</blockquote>
<p>웹 사이트 접속 후 &gt; 계정 생성
<br /></p>
<h4 id="📄-aws-관리-콘솔-페이지로-이동">📄 AWS 관리 콘솔 페이지로 이동</h4>
<blockquote>
<p>모든 서비스를 열어서, 스토리지 항목 &gt; S3 페이지로 이동</p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/b78f2c3a-be7a-483a-8b66-e8b3712eae0f/image.png" /></p>
<br />

<h4 id="📄-버킷-만들기">📄 버킷 만들기</h4>
<blockquote>
<p><code>버킷 만들기</code> 버튼을 클릭해서 버킷 생성</p>
</blockquote>
<p>☑️ *<em>버킷이란? *</em>
S3에서 파일을 모아두는 큰 단위
☑️ *<em>S3란? *</em>
구글 드라이브 같은 저장소라고 이해하기
<br /></p>
<p>❗<strong>버킷 이름은 도메인 이름과 동일하게 작성해주기!</strong>
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/ef5e99db-3a25-4217-9c6b-e376e3e50846/image.png" /></p>
<h4 id="📄-아래-사진과-같이-설정">📄 아래 사진과 같이 설정</h4>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/8fd819cb-0702-4073-b31d-1a7c7c59ece9/image.png" /></p>
<h4 id="📄-버킷-이름-클릭">📄 버킷 이름 클릭</h4>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/d03e09f9-8d42-4e0e-be55-9025b7dd5b18/image.png" /></p>
<h4 id="📄-속성-탭-클릭--정적-웹-사이트-호스팅-항목--편집-버튼-클릭--활성화-체크">📄 [속성] 탭 클릭 &gt; [정적 웹 사이트 호스팅] 항목 &gt; [편집] 버튼 클릭 &gt; [활성화] 체크</h4>
<blockquote>
<p>정적 웹 사이트 호스팅: 만든 파일을 웹 사이트로 만드는 것</p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/8311458a-1031-41fd-9180-fdae254f9ada/image.png" /></p>
<h4 id="📄-두-입력-필드에-indexhtml-넣기">📄 두 입력 필드에 index.html 넣기</h4>
<p>🌠 <strong>오류 문서는 파일이 없는 경로로 접속하는 경우에 보여줄 HTML 파일이다. 
index.html 넣으면 경로 처리를 리액트로 할 수 있다는 장점이 있음.</strong></p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/d9e3e185-38fc-4767-98be-22a9bd1abba3/image.png" /></p>
<h4 id="📄-다시-돌아와서-권한-탭-클릭--버킷-정책-항목--편집-버튼-클릭--정책-생성기-버튼-클릭">📄 다시 돌아와서, [권한] 탭 클릭 &gt; [버킷 정책] 항목 &gt; [편집] 버튼 클릭 &gt; [정책 생성기] 버튼 클릭</h4>
<p>🌠 <strong>버킷 ARN 복사해두기</strong>
<br /></p>
<h4 id="📄-step-1-s3-bucket-policy-옵션-선택">📄 Step 1: [S3 Bucket Policy] 옵션 선택</h4>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/23c339b6-4641-41b1-9f83-c1652a1e3ec4/image.png" /></p>
<h4 id="📄-step-2-하단-이미지와-같이-설정-복사한-버킷-arn-붙여넣은-뒤에다-codecode-적기--add-statement-클릭">📄 Step 2: 하단 이미지와 같이 설정 (복사한 버킷 ARN 붙여넣은 뒤에다 <code>/*</code> 적기) &gt; [Add Statement] 클릭</h4>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/e77ad0b8-9147-4a14-9cde-fbecf9a4c5e9/image.png" /></p>
<h4 id="📄-generate-policy-클릭--json-코드-복사하고--정책에-붙여넣는다--변경-사항-저장-버튼-클릭">📄 [Generate Policy] 클릭 &gt; JSON 코드 복사하고 &gt; 정책에 붙여넣는다. &gt; [변경 사항 저장] 버튼 클릭</h4>
<p>배포에 대한 모든 설정이 끝났다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/0c2c6951-7828-4639-b026-a1f1a427cf82/image.png" /></p>
<h4 id="❗-마지막으로-빌드-파일-업로드해보기">❗ <strong>마지막으로 빌드 파일 업로드해보기!</strong></h4>
<p>다시 돌아와서, [객체] 탭 클릭 &gt; [업로드] 버튼 클릭 &gt; 배포하고 싶은 프로젝트의 [bulid] 폴더 안에 있는 모든 파일들을 드래그 해서 끌어다 놓고 &gt; 하단 [업로드] 버튼 클릭
<br /></p>
<h4 id="❗-이제-프로젝트에-직접-접속해보기">❗ <strong>이제 프로젝트에 직접 접속해보기!</strong></h4>
<p>업로드가 완료되면 [닫기] 버튼을 누르고 &gt; [속성] 탭 클릭 &gt; 아까 봤던 [정적 웹 사이트 호스팅] 항목에 [버킷 웹 사이트 엔드포인트]라는 내용과 <strong>프로젝트 주소가 생성</strong>된 것을 볼 수 있다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/41dee192-356f-4ecd-ada6-a99c5bd81fa8/image.png" /></p>
<br />

<hr />
<br />


<h2 id="✅-커스텀-도메인-달기aws-route53">✅ 커스텀 도메인 달기(AWS Route53)</h2>
<br />


<h3 id="🌠-1-1-aws를-통해-등록">🌠 1-1) AWS를 통해 등록</h3>
<br />

<p><strong>1. AWS에서 도메인 구입</strong></p>
<blockquote>
<p>'Route 53' 검색 &gt; 도메인 &gt; 등록된 도메인 메뉴 &gt;  도메인 등록</p>
</blockquote>
<p>☑️ Route 53을 사용하면 AWS로 도메인을 관리할 수 있다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/f56bfcff-5964-4810-b04d-904e71485044/image.png" /></p>
<p><strong>2. 도메인 이름 선택 화면 &gt; 도메인 검색(예시 codeit)</strong></p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/881df95c-389e-4090-814a-75f3c9e5ac9a/image.png" /></p>
<p><strong>3. 안내에 따라 구매 완료</strong></p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/152ce269-e368-42ab-9545-72d593176911/image.png" /></p>
<p>*<em>4. 도메인을 구입하고나서 Route 53에 있는 호스팅 영역 메뉴에 들어가면, 아까 구입한 도메인이 호스팅 영역이란 걸로 생성되었다.
*</em>
☑️ Route 53에서는 호스팅 영역을 단위로 도메인을 관리한다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/a53c65f5-a00b-43e2-b46c-7be8db0dcc87/image.png" /></p>
<p><strong>5. 도메인 이름 클릭해서 확인</strong></p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/244153a2-57b5-4822-8189-88600e14e2f8/image.png" /></p>
<p><br /><br /></p>
<h3 id="🌠-1-2-도메인을-이미-구입한-상황">🌠 1-2) 도메인을 이미 구입한 상황</h3>
<p>다른 사이트에서 구입한 도메인을 AWS에서 관리하려면 몇 가지 설정이 필요하다.
<br /></p>
<p><strong>1. AWS로 접속해서 'Route 53'을 검색 &gt; 호스팅 영역 메뉴 &gt; 호스팅 영역 생성 버튼을 클릭</strong></p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/c495ac49-52c2-452d-bc12-c2386f3d620c/image.png" /></p>
<p><strong>2. 도메인 이름은 다른 사이트에서 구입한 도메인명을 적고, 호스팅 영역 생성 버튼을 눌러서 생성.</strong></p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/d8fc6849-084b-4f75-b3d1-5db42784554f/image.png" /></p>
<p><strong>3.  호스팅 영역이 만들어지고, 기본 값들이 설정</strong>
(❗유형이 NS인 네임서버 레코드에 주목)</p>
<p>☑️ 여기서 레코드는 도메인을 서비스할 때 참고할 정보</p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/32bafa15-1a60-40b7-b8f0-3fe06348ab46/image.png" /></p>
<ol start="4">
<li><strong>도메인을 구입하신 사이트에 들어가서, '네임서버 설정'을 해줘야한다.
이용하는 사이트 도메인 관리 페이지 &gt; AWS 호스팅 영역에서 기본 값으로 생성된 레코드 중에서 NS 유형에 해당하는 값/트래픽 라우팅 대상의 값을 복사해서 커스텀 네임서버로 등록</strong>
<br /><br /></li>
</ol>
<h3 id="🌠-2-a-레코드-등록하기">🌠 2) A 레코드 등록하기</h3>
<p>Route 53의 호스팅 영역에 A 레코드를 등록해보기</p>
<blockquote>
<p>A 레코드는 웹 브라우저가 도메인 주소로 들어왔을 때, 어떤 주소의 서버가 응답해 줄지 지정해주는 용도로 쓴다.</p>
</blockquote>
<p><strong>1. 앞에서 만든 호스팅 영역에서 레코드 생성 버튼을 클릭</strong></p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/3f958464-c255-4f95-9832-a5c68e5a1510/image.png" /></p>
<p><strong>2. 아래 예시는 레코드 이름을 dicegam라고 했는데, '<u>dicegame.react.pizza</u>' 를 사용하려고 이렇게 만든 것.</strong></p>
<p>☑️ 레코드 유형은 A
☑️ 트래픽 라우팅 대상에서 별칭 켜기 <em>(별칭은 AWS에서 제공하는 기능인데, 만들어 놓은 S3 버킷의 엔드포인트(주소)를 직접 입력하지 않아도 되고, AWS 안에서 별명처럼 쓸 수 있게 해준다.)</em>
<br /></p>
<p>❗ <strong>만약에 react.pizza 라는 주소로 만들고 싶다면, 버킷 이름도 반드시 react.pizza 로 해줘야 한다는 것에 주의</strong></p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/39a1c5dc-732c-49ea-97ee-8e59e935818f/image.png" /></p>
<ol start="3">
<li>모두 설정하고 레코드 생성 버튼을 클릭하면, 호스팅 영역에 A 레코드가 생겼다.</li>
</ol>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/c5ab1209-527a-46c6-aaba-17b35baf34a9/image.png" /></p>
<br />

<h3 id="🌠-잘-적용되었는지-확인하는-법">🌠 잘 적용되었는지 확인하는 법</h3>
<blockquote>
<p><a href="https://dnschecker.org">https://dnschecker.org</a> 접속</p>
</blockquote>
<p>☑️ A 레코드를 선택하고, 아까 만든 주소를 검색
☑️ 초록색 체크 표시랑 아이피 주소가 잘 보이신다면 잘 적용된 것.</p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/f148a994-2891-4470-94f6-4c682cd4d5ea/image.png" /></p>
<br />
<br />

<h3 id="❓브라우저는-어떻게-리액트를-알아들을까">❓브라우저는 어떻게 리액트를 알아들을까?</h3>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/2e15ea26-ba13-467b-80a5-61ca037f12fe/image.png" /></p>
<h4 id="📄-babel">📄 babel</h4>
<p><a href="https://babeljs.io/">babel 공식 홈페이지</a></p>
<p>JSX가 어떻게 순수 자바스크립트로 번역되는지 확인할 수 있다.
Try it out 메뉴로 들어가면 영상에서 나온 트랜스파일링을 직접 해 볼 수 있다.
<br /></p>
<hr />
<h2 id="참고자료">참고자료</h2>
<p>코드잇 | 리액트 배포하기</p>