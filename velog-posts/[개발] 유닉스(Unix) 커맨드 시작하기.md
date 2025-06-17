<p>거의 다 작성했는데 날아가서 새로 쓴다 . . . ☺️
저장이 하나도 안됐는데 자동 저장 기능은 도대체 왜. 있는. 건즤. ? 
<br /></p>
<img src="https://velog.velcdn.com/images/iamsuuya/post/f337fa25-e456-4e68-95a7-adbef3e64546/image.jpg" width="360px" />
<br />
싸우자 . . .  &nbsp;싸우자고 . . . .<br />
싸우자 . . .  &nbsp;싸우자고 . . . .<br />
싸우자 . . .  &nbsp;싸우자고 . . . .

<p>💻💥🤛🏻🐿️
<br /><br /><br /></p>
<h2 id="✅-유닉스unix란">✅ 유닉스(Unix)란?</h2>
<blockquote>
<p>유닉스는 1969년 AT&amp;T Bell Labs 연구원들에 의해 개발된 컴퓨터 운영 체제의 하나로, <strong>개발자들이 소프트웨어를 개발하고 실행할 수 있는 편리한 플랫폼을 제공하기 위해 개발</strong>되었다. </p>
</blockquote>
<p>우리가 사용하는 macOS, Linux, Ubuntu 모두 유닉스에서 파생.</p>
<p>사람이 이해하기 쉬운 고급 프로그래밍 언어, C로 대부분 작성되었기 때문에 당시 큰 인기를 끌었고, 유닉스를 수정해서 다른 컴퓨터에 적용하는 사례가 많아지다보니 많은 변형판과 파생 운영 체제를 낳았다. 다양한 하드웨어 플랫폼에서 작동할 수 있는 높은 이식성을 가지고 있다. 
<br /></p>
<h3 id="리눅스"><strong>리눅스</strong></h3>
<p>유닉스는 AT&amp;T의 소유였기 때문에 사용 시 라이선스 비용이 필요했다. 
<span style="color: #999;"><em>(이 당시에도 소프트웨어를 더 쉽고 자유롭게 공유해야 프로그래밍이 더 발전할 수 있다고 생각하는 공유의 문화가 있었다.)</em></span> </p>
<p>이를 반대한 자유 소프트웨어 재단에서 GNU 프로젝트가 시작되었고, 유닉스 없이 유닉스와 유사한 운영 체제를 만들어 누구나 쉽게 사용하거나 변형할 수 있는 무료 버전을 만들어 배포하고자 했다. </p>
<p>그러나 핵심인 커널이 없던 GNU에 핀란드 학생 리누스 토발즈가 만든 리눅스 커널이 더해지며 GNU/Linux가 완성되었고, 개인용 컴퓨터, 스마트폰, 자동차, 가전제품, 슈퍼컴퓨터 등 다양한 분야에 범용적으로 사용되고 있다.
<br /></p>
<h3 id="이-모든-운영-체제의-공통점">이 모든 운영 체제의 공통점</h3>
<p>리눅스와 리눅스의 변형 OS, macOS 모두 유닉스의 표준을 사실상 거의 다 만족한다는 것. 
그래서 사용하는 커맨드가 모두 비슷하다. 개발에서 유닉스 커맨드가 가장 보편적으로 사용하기 때문에 <strong>유닉스 커맨드</strong>라고 부른다. </p>
<p><br /><br /></p>
<h2 id="✅-프로그램-설치">✅ 프로그램 설치</h2>
<h3 id="💿-wsl-설치하기">💿 WSL 설치하기</h3>
<p>WSL은 Windows Subsystem for Linux(리눅스용 윈도우 하위 시스템)의 약자. 
<strong>리눅스 커맨드와 커맨드라인 앱을 윈도우에서 실행할 수 있게 하는 가벼운 툴</strong>이다.
<br /></p>
<p><strong>Windows 개인 컴퓨터에서 실습하기</strong></p>
<ol>
<li>윈도우 메뉴에 <code>powershell</code> 검색 &gt; <code>관리자로 실행</code> 클릭</li>
<li>아래 커맨드를 복사해서 <code>PowerShell</code>에 붙여넣기 &gt; <code>엔터</code> (WSL 사용 허용)
<code>dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart</code></li>
<li>컴퓨터 재부팅</li>
<li>윈도우 메뉴에 <code>Microsoft Store</code> &gt; <code>Ubuntu</code> 검색 &gt; <code>설치</code> 
🌠 <strong>버전이 따로 없는게 가장 최신 LTS(장기 지원 버전) 버전</strong>이다.</li>
<li>다운로드 후 <code>열기</code> &gt; WSL <code>실행</code></li>
</ol>
<ul>
<li><code><strong>Enter new UNIX username</strong></code> : 사용자 이름</li>
<li><code><strong>New password</strong></code> : 비밀번호 입력</li>
<li><code><strong>Retype new password</strong></code> : 비밀번호 재입력</li>
</ul>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;🌠 <strong>비밀번호 입력 시 화면에 아무런 변화가 없는게 정상이다.</strong><br />
사용 준비 완료. </p>
<p><code>$</code> 기호 뒤에 커맨드를 입력해 사용하면 된다.
<br /><br /></p>
<h2 id="✅-가상-머신virtual-machine이란">✅ 가상 머신(Virtual Machine)이란?</h2>
<blockquote>
<p>사용자가 사용하는 <strong>컴퓨터 안에 있는 또 다른 가상의 컴퓨터</strong></p>
</blockquote>
<p>즉, 내가 윈도우를 쓰고 있더라도 그 안에서 가상 머신을 만들고, 그 가상 머신에 리눅스 배포판 중 하나를 설치하면 리눅스 환경을 사용할 수 있다. 가상 머신을 만들려면 그걸 가능하게 해주는 프로그램을 설치해야 하는데, 가상화 프로그램에는 여러 가지가 있다.</p>
<h3 id="💿-virtualbox-설치하기">💿 VirtualBox 설치하기</h3>
<ol>
<li><code>VirtualBox</code> 다운로드 페이지 &gt; <code>Windows hosts</code> 클릭 &gt; 설치 파일 <code>다운로드</code>
🌠 <strong>VirtualBox 설치 페이지</strong>: <a href="https://www.virtualbox.org/wiki/Downloads">https://www.virtualbox.org/wiki/Downloads</a></li>
<li>다운로드한 설치 파일 <code>실행</code> &gt; <code>Next</code> 또는 <code>Yes</code> 버튼을 눌러서 쭉 진행</li>
<li>마지막으로 <code>Install</code> 버튼 클릭 &gt; <code>설치</code></li>
<li>설치 완료 &gt; <code>Finish</code> 버튼 &gt; <code>창 닫기</code>
<br /><br /><br /></li>
</ol>
<h2 id="✅-가상-머신-생성--우분투ubuntu-설치하기">✅ 가상 머신 생성 + 우분투(Ubuntu) 설치하기</h2>
<p>VirtualBox로 가상 머신을 생성하는 방법과 리눅스 배포판 중 하나인 우분투를 설치하는 방법</p>
<h3 id="💿-우분투-설치하기">💿 우분투 설치하기</h3>
<ol>
<li><code>우분투</code> 다운로드 페이지 &gt; <code>Download</code>버튼 클릭 &gt; <code>.iso</code>로 끝나는 파일 다운로드 확인
🌠 <strong>우분투 설치 페이지</strong>: <a href="https://ubuntu.com/download/desktop">https://ubuntu.com/download/desktop</a><br />

</li>
</ol>
<h3 id="💿-가상-머신-생성">💿 가상 머신 생성</h3>
<p>💡 <strong>Ubuntu 24.04.2 LTS Ver.</strong>에 대한 설치 방법이다.</p>
<ol>
<li>VirtualBox 화면 &gt; <code>새로 만들기</code> 버튼 클릭</li>
<li>가상 머신의 기본 정보를 설정하는 창.</li>
</ol>
<ul>
<li>이름: 가상 머신의 이름. 원하는 대로 작성.</li>
<li>종류: Linux</li>
<li>버전: Ubuntu(64bit) 
(가상 머신에 리눅스 배포판 중의 하나인 우분투를 설치할 것이라는 뜻)
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/efa9a445-253b-4693-8772-025e96b8d617/image.png" /></li>
</ul>
<ol start="3">
<li>가상 머신의 메모리 크기를 설정할 수 있는 창.
메모리가 너무 작으면 가상 머신의 속도가 느릴 수 있기 때문에 메모리 크기를 <code>4GB,(=4096MB)</code>로 설정
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/c80144b7-fe42-4c02-9486-4f722de85b9e/image.png" /></li>
<li>가상 하드 디스크의 용량을 설정하는 창. 
넉넉하게 <code>20GB</code>로 설정 &gt; <code>완료</code> 클릭
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/91de5102-3b63-4ab2-b3a4-2b333d1b6c88/image.png" /></li>
<li>*<em>생성된 가상 머신에 우분투 설치 방법 *</em>
가상 머신 <code>생성</code> &gt; <code>저장소</code>영역 <code>[광학 드라이브] 비어 있음</code> 클릭 &gt; <code>Choose/Create a Disk Image..</code> 클릭
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/30394797-c1ba-43cb-a669-2533a24a609b/image.png" /></li>
<li><code>추가</code> 버튼 클릭 &gt; 아까 다운로드 받은 <code>우분투 설치 파일</code>(이름이 .iso로 끝나는 파일) 선택 &gt; <code>열기</code> 클릭
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/78235213-b733-4085-98bf-075163db3030/image.png" /></li>
<li>해당 우분투 설치 파일이 가상 머신에 인식. 
우분투 설치 파일이 들어있는 CD를 가상 머신에 넣은 거라고 생각하면 된다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/7917ff0e-68c3-45f0-b951-76c9b7393fec/image.png" /></li>
<li><code>시작</code> 버튼 클릭 &gt; 가상 머신이 부팅되고 우분투 파일이 실행된다.
<br /><br /></li>
</ol>
<h4 id="💿-마지막-가상-머신에-우분투-설치">💿 마지막, 가상 머신에 우분투 설치</h4>
<p>실행된 가상 머신에 아래와 같이 설치하면 끝!
중간에 단계를 건너 뛴 것도 있는데 언어 설정과 같은 부분이라 자유롭게 설정하면 된다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/856cdfea-2ba8-4209-9fc6-b9b5ad50f349/image.png" /><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/5b513516-97d7-42c3-adf4-82056fe05f3b/image.png" /><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/7b9dfd47-ac9d-4e94-8e7f-2856dc945fd0/image.png" /><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/3885bfd3-e2dd-4315-a2f5-fe8536028278/image.png" /><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/c22b020c-0d65-40b6-9fe2-225d98ec861e/image.png" />끝 . .
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/91935bf7-9bc6-4d15-aa53-705ae7c44d60/image.png" /></p>
<p>이것이 바로 우분투의 GUI(Graphic User Interface) 환경.
<br /></p>
<h4 id="🌠-virtualbox-화면-조정-문제-해결하기">🌠 VirtualBox 화면 조정 문제 해결하기</h4>
<p>가상 머신 화면의 크기를 늘려도 실제 우분투의 바탕 화면 크기는 늘어나지 않는다면,</p>
<ol>
<li><code>장치</code> 탭의 <code>게스트 확장 CD 이미지 삽입</code>이라는 탭을 클릭</li>
<li><code>Run</code> 버튼을 클릭</li>
</ol>
<p>다시 시작하면 머신의 화면 크기를 늘리면 그에 맞게 우분투의 바탕 화면도 커지는 것을 확인할 수 있다.
<br /><br /></p>
<p>우분투를 사용할 준비가 끝났다. 👏🏻
<br /></p>
<hr />
<h2 id="참고자료">참고자료</h2>
<p>코드잇 &lt;유닉스 커맨드 시작하기&gt; 토픽</p>