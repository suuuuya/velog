<p>탈모 걸린 내 잔디밭..
블로그라도 열심히 써서 풍성하게 만들어 보겠습니댜.<br /></p>
<blockquote>
<p>기술 블로그 운영하면서 <strong>깃허브 잔디 심는 법</strong> 💻🪴</p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/0db2bebc-3e99-460e-a1c8-5294423b451a/image.png" /></p>
<p>1일 1잔디, 부지런히 채워보자 ★
<br /><br /></p>
<h2 id="✅-레파지토리repository-생성">✅ 레파지토리(Repository) 생성</h2>
<p><br />1. <strong>New repository</strong> &gt; <strong>Repository name*</strong> 작성  &gt; <strong>'Public'</strong> 체크 ✅ &gt;  <strong>Create repository</strong><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/d2bb6ed4-0b1c-41cd-947d-23f9e4f00cc4/image.png" />
<br /></p>
<h2 id="✅-update_blogyml-파일-생성">✅ update_blog.yml 파일 생성</h2>
<p><br />2. <strong>생성된 레파지토리</strong>의** Actions** &gt; <strong>Simple Workflow</strong> &gt; <strong>Configure</strong> <img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/343250c0-58a9-4d10-9f12-77dc0ceda237/image.png" /></p>
<p>*<em>파일 경로 : *</em><code>.github/workflows/update_blog.yml</code>
위의 파일 경로를 붙여 넣으면 update_blog.yml의 폴더까지 함께 생성된다.
🌠 <u>아래와 같이 동일한 브랜치</u>인지 확인</p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/5d008f4e-8ea8-4af7-8f00-7663bdb68909/image.png" /><strong>Edit</strong> &gt; 하단 <strong>소스</strong> 붙여넣기<strong>(<u>본인 계정으로 변경</u>)</strong> &gt; <strong>Commit changes</strong></p>
<p><code>1.main or master</code>
<code>2.깃허브아이디</code></p>
<pre><code class="language-javascript">name: Update Blog Posts

on:
  push:
      branches:
        - 1.main or master  # 또는 워크플로우를 트리거하고 싶은 브랜치 이름
  schedule:
    # 테스트를 원한다면, `한국 표준시 = UTC + 9` 참고해서 시간 수정한 후 테스트해보기
    - cron: '0 0 * * *'  # 매일 자정에 실행, UTC 협정 세계시 기준 (한국 시간 기준 오전 9시)
    - cron: '0 15 * * *' # 매일 자정에 실행, 한국 시간 기준 (UTC 15:00)

jobs:
  update_blog:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout
      uses: actions/checkout@v2

    - name: Push changes
      run: |
        git config --global user.name 'github-actions[bot]'
        git config --global user.email 'github-actions[bot]@users.noreply.github.com'
        git push https://${{ secrets.GH_PAT }}@github.com/2.깃허브아이디/velog.git

    - name: Set up Python
      uses: actions/setup-python@v2
      with:
        python-version: '3.x'

    - name: Install dependencies
      run: |
        pip install feedparser gitpython

    - name: Run script
      run: python scripts/update_blog.py</code></pre>
<p><br /><br /></p>
<h2 id="✅-update_blogpy-파일-생성">✅ update_blog.py 파일 생성</h2>
<p><br />3. <strong>생성한 레파지토리</strong> &gt; <strong>Add file</strong> &gt; <strong>Create new file</strong>
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/6e9bc1cc-ab24-4f7b-a0b3-ca14a6e7e57a/image.png" /><strong>파일 경로 : **<code>scripts/update_blog.py</code>
위의 파일 경로를 붙여 넣으면 update_blog.py의 폴더까지 함께 생성된다.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/bdf983f4-eee4-4857-85f8-c5e158e2385e/image.png" /></strong>Edit** &gt; 하단 <strong>소스</strong> 붙여넣기<strong>(<u>본인 계정으로 변경</u>)</strong> &gt; <strong>Commit changes</strong></p>
<p><code>1.벨로그아이디</code></p>
<pre><code class="language-javascript">import feedparser
import git
import os

# 벨로그 RSS 피드 URL
rss_url = 'https://api.velog.io/rss/1.벨로그아이디'

# 깃허브 레포지토리 경로
repo_path = '.'

# 'velog-posts' 폴더 경로
posts_dir = os.path.join(repo_path, 'velog-posts')

# 'velog-posts' 폴더가 없다면 생성
if not os.path.exists(posts_dir):
    os.makedirs(posts_dir)

# 레포지토리 로드
repo = git.Repo(repo_path)

# RSS 피드 파싱
feed = feedparser.parse(rss_url)

# 각 글을 파일로 저장하고 커밋
for entry in feed.entries:
    # 파일 이름에서 유효하지 않은 문자 제거 또는 대체
    file_name = entry.title
    file_name = file_name.replace('/', '-')  # 슬래시를 대시로 대체
    file_name = file_name.replace('\\', '-')  # 백슬래시를 대시로 대체
    # 필요에 따라 추가 문자 대체
    file_name += '.md'
    file_path = os.path.join(posts_dir, file_name)

    # 파일이 이미 존재하지 않으면 생성
    if not os.path.exists(file_path):
        with open(file_path, 'w', encoding='utf-8') as file:
            file.write(entry.description)  # 글 내용을 파일에 작성

        # 깃허브 커밋
        repo.git.add(file_path)
        repo.git.commit('-m', f'Add post: {entry.title}')

# 변경 사항을 깃허브에 푸시
repo.git.push()</code></pre>
<p><br /><br /></p>
<h2 id="✅-pat-권한-받기">✅ PAT 권한 받기</h2>
<p><br />4. <strong>내 GitHub 계정</strong> &gt; <strong>Settings</strong>
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/0648d86b-36be-40d9-a040-4057517b43e9/image.png" /></p>
<p><strong>경로</strong> : 
<strong>Settings</strong> &gt; <strong>Developer settings(최하단에 있음)</strong> &gt; <strong>Personal access tokens</strong> &gt; <strong>Tokens (classic)</strong> &gt; <strong>Generate new token</strong> &gt; *<em>Generate new token (classic) *</em></p>
<p><strong>작성/체크</strong> :
<strong>토큰 이름 작성(Note)</strong> &gt; <strong>repo, workflow</strong> 체크 ✅ &gt; <strong>Generate token</strong></p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/25b8d8b5-8cb0-4e06-9b62-dec043a821c4/image.png" />
<br /></p>
<h2 id="✅-토큰-복사">✅ 토큰 복사</h2>
<p><br />5. 창을 벗어나면 이후에는 <strong>토큰 확인이 불가하니 꼭 복사</strong> 해두기
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/3787e758-5b54-4605-bff1-40a10d13b135/image.png" />
<br /></p>
<h2 id="✅-토큰-붙여넣기">✅ 토큰 붙여넣기</h2>
<p><br />6. <strong>velog 레파지토리</strong> &gt; <strong>Settings</strong> &gt; <strong>Secrets and Variables</strong> &gt; <strong>Actions</strong> &gt; <strong>New repository secret</strong>
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/560ba0b7-a96d-4c73-873e-dcda8ee0dffd/image.png" /></p>
<p><strong>Name*</strong>, <strong>Secret*</strong> 작성 &gt; <strong>Add secret</strong></p>
<p>-&nbsp;<strong>Name</strong> : GH_PAT
-&nbsp;<strong>Secret</strong> : 위에서 복사한 토큰 붙여넣기
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/318d46a3-a9a8-4ea5-92ba-d5fe91a551fa/image.png" />
<br /></p>
<h2 id="✅-레파지토리에-외부-권한-부여">✅ 레파지토리에 외부 권한 부여</h2>
<p><br />7. <strong>velog 레파지토리</strong> &gt; <strong>Settings</strong> &gt; <strong>Actions</strong> &gt; <strong>General</strong> 
아래 이미지와 같이 체크 ✅, 각 항목 변경할 때마다 <code>Save</code> 클릭</p>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/cbf2fb8f-a1ea-4235-8f48-560721517309/image.png" /><br /></p>
<h2 id="✅-결과-🌴🌲🌳">✅ 결과 🌴🌲🌳</h2>
<p>반영된 화면.
<img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/b20c6fdd-45ac-465d-9aee-19d2f84ef490/image.png" /><br /></p>
<hr />
<h2 id="참고자료">참고자료</h2>
<p><a href="https://velog.io/@ryuneng2/GitHub-velog%EC%99%80-GitHub-%EC%97%B0%EB%8F%99%ED%95%98%EA%B8%B0-velog-%EA%B8%80-%EC%9E%91%EC%84%B1-%EC%8B%9C-%EC%9E%90%EB%8F%99%EC%9C%BC%EB%A1%9C-%EA%B9%83%ED%97%88%EB%B8%8C%EC%97%90-%EC%BB%A4%EB%B0%8B%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95">https://velog.io/@ryuneng2/GitHub-velog와-GitHub-연동하기-velog-글-작성-시-자동으로-깃허브에-커밋하는-방법</a></p>