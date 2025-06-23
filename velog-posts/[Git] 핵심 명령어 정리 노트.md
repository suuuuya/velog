<h2 id="✅-기본-커맨드-써보기">✅ 기본 커맨드 써보기</h2>
<pre><code class="language-bash"># 1. 현재 디렉토리를 Git 레포지토리로 초기화
git init

# 2. 사용자 이름과 이메일 설정
git config user.name 'suya'
git config user.email 'suya@gmail.com'  

# 3. 파일을 staging area에 추가
# 특정 파일 추가 (예시: example.txt)
git add example.txt

# 특정 디렉토리 추가 (예시: src/)
git add src/

# 현재 디렉토리 전체 변경 사항 staging area에 올리기
git add .

# 4. staging area에서 특정 파일 제거 
# (예시: example.txt를 staging area에서 내리기)
git reset example.txt

# 5. 현재 상태 확인
git status

# 6. 커밋 메시지
git commit -m &quot;커밋 메시지&quot;

# 7. Git 도움말 보기 (예시: commit 명령어에 대한 도움말)
git help commit</code></pre>
<p><br /><br /></p>
<h2 id="✅-github-커맨드">✅ GitHub 커맨드</h2>
<pre><code class="language-bash"># 1. 로컬 레포지토리를 원격 저장소(GitHub 등)와 연결하고 첫 푸시

# -u 또는 --set-upstream 옵션은 로컬 브랜치와 원격 브랜치를 연결
git push -u origin master  # 최초 1회만 필요

# 이후부터는 단순하게 아래 명령어로 푸시 가능
# 로컬의 변경사항을 원격 저장소로 푸시
git push 

🌠 다른 사람도 push할 수 있도록 하려면:
🌠 GitHub 저장소 설정에서 해당 사용자를 Collaborator로 추가해야 함


# 2. 원격 저장소의 변경사항을 로컬로 가져오기
git pull  # 병합도 함께 수행됨

# 3. GitHub에 있는 프로젝트를 로컬로 복제하기 (예시 URL 사용)
git clone https://github.com/사용자명/레포지토리명.git</code></pre>
<p><br /><br /></p>
<h2 id="✅-커밋-커맨드">✅ 커밋 커맨드</h2>
<pre><code class="language-bash"># 1. 커밋 히스토리 전체 보기
git log

# 2. 커밋 히스토리를 한 줄씩 간단하게 출력 (커밋 ID + 메시지)
git log --pretty=oneline

🌠 pretty 포맷 참고:
자세한 출력 형식은 공식 문서 참조: https://git-scm.com/docs/pretty-formats

# 3. 특정 커밋의 상세 내용 보기 (예: 커밋 변경사항 확인)
git show [커밋 아이디]
e.g.) git show abc1234

# 4. 가장 최근 커밋 수정 (메시지나 스테이지된 파일 변경 등)
git commit --amend

# 5. 커맨드에 별칭(alias) 붙이기
git config alias.[별명] [커맨드]

e.g.) 'git co'로 'git checkout' 실행하도록 설정
git config alias.co checkout
git config alias.st status
git config alias.br branch

# 6. 두 커밋 사이의 차이 비교
git diff [커밋 A의 아이디] [커밋 B의 아이디]
e.g.) git diff abc1234 def5678

# 7. 특정 커밋으로 리셋 (옵션에 따라 리셋 범위가 다름)
git reset --soft abc1234   # HEAD만 이동
git reset --mixed abc1234  # HEAD + staging area 초기화
git reset --hard abc1234   # HEAD + staging area + working directory까지 되돌림

🌠 옵션을 생략하면 기본은 --mixed 가 적용됨

# 8. 특정 커밋에 태그 달기
git tag [태그 이름] [커밋 아이디]
e.g.) git tag v1.0.0 abc1234  # 원하는 태그 이름과 커밋 ID 사용</code></pre>
<p><br /><br /></p>
<h2 id="✅-브랜치-커맨드">✅ 브랜치 커맨드</h2>
<pre><code class="language-bash"># 1. 새 브랜치 생성
git branch [새 브랜치 이름]
git branch new-feature  # 'new-feature'는 원하는 브랜치 이름으로 바꿔 사용

# 2. 새 브랜치 생성 + 생성한 브랜치로 즉시 이동
git checkout -b [새 브랜치 이름]
git checkout -b new-feature

# 3. 기존 브랜치로 이동
git checkout [기존 브랜치 이름]
git checkout main  # 또는 master 등 원하는 브랜치 이름

# 4. 브랜치 삭제
git branch -d [기존 브랜치 이름]
git branch -d old-feature  # 병합하지 않은 브랜치는 -D 옵션으로 강제 삭제 가능

# 5. 현재 브랜치에 다른 브랜치를 병합
git merge [기존 브랜치 이름]
git merge new-feature  # 현재 브랜치에 'new-feature' 브랜치 내용을 합침

# 6. 머지 도중 충돌(conflict) 발생 시, 머지 취소하고 이전 상태로 되돌리기
git merge --abort

# 🌠 conflict(충돌): 두 브랜치에서 같은 부분을 다르게 수정했을 때 발생
# - 충돌이 생긴 파일을 수동으로 수정 후 `git add`로 스테이징하고 `git commit`으로 마무리
# - 충돌 파일이 너무 많거나 머지를 미루고 싶다면 `git merge --abort`로 되돌릴 수 있음</code></pre>
<h4 id="📚-브랜치-관련-지식">📚 브랜치 관련 지식</h4>
<p><code>origin</code> : 리모트 레포지토리를 가리킬 때 쓰이는 단어.</p>
<ul>
<li>리모트(remote)는 Git에서 원격 저장소를 의미<br />

</li>
</ul>
<p><code>upstream</code> : Git에서 원격 저장소를 가리키는 데 사용되는 용어. 로컬 브랜치에서 어떤 변경 사항이 있을 때, 이 변경 사항을 반영할 원격 브랜치를 upstream 브랜치라고 한다.</p>
<pre><code class="language-bash">git push --set-upstream origin &lt;branch-name&gt;</code></pre>
<p>위 명령어를 실행하면 특정 로컬 브랜치가 원격 저장소의 특정 브랜치를 추적하도록 설정할 수 있다. 이후부터는 그냥 git push, git pull이라고만 써도 편하게 푸시와 풀을 할 수 있게 된다.
<br /><br /></p>
<h2 id="✅-git-협업-실전-커맨드">✅ Git 협업 실전 커맨드</h2>
<pre><code class="language-bash"># 1. 원격 저장소의 최신 내용을 가져오기 (병합은 하지 않음)
git fetch

# 🌠 git fetch는 최신 변경사항을 **가져오기만** 함
# 예: 원격 브랜치의 변경 내용을 먼저 확인하고 싶을 때 사용
# 이후 필요하면 머지하거나 리베이스해서 적용

# 2. 파일의 각 줄이 어떤 커밋에서 작성되었는지 추적
git blame example.py  # 'example.py'는 추적할 파일명으로 교체

# 3. 특정 커밋을 되돌리는 새로운 커밋 생성
git revert abc1234  # 되돌리고 싶은 커밋 ID 사용

# 🌠 git revert는 기존 히스토리를 보존한 채 되돌림
# 협업 중에는 reset보다 revert가 안전 (히스토리 공유에 영향이 없음)</code></pre>
<hr />
<pre><code class="language-bash"># 1. HEAD가 이동한 모든 커밋의 히스토리 보기 (리셋 전 등 되돌리기 유용)
git reflog

# 2. 모든 브랜치 커밋을 그래프로 보기 (브랜치 간 관계를 시각적으로 확인)
git log --all --graph

# 3. 리베이스 실행 (브랜치를 깔끔하게 이어붙이기)
# 예: 현재 브랜치가 A이고, B 브랜치의 최신 커밋 뒤에 A 브랜치의 커밋들을 붙이기
git rebase B  # B는 기준이 되는 브랜치명

# 🌠 rebase는 커밋 히스토리를 병합 대신 '깔끔하게 직렬화'하고 싶을 때 사용

# 4. 현재 작업 디렉토리의 변경사항 임시 저장 (작업 중단 시 사용)
git stash

# 5. 저장해뒀던 작업 복원 (apply: 적용만, pop: 적용 + 삭제)
git stash apply stash@{0}     # 가장 최근 저장된 stash 적용 (ID는 선택적)
git stash pop stash@{0}       # 적용 후 stash에서 제거
git stash drop stash@{0}      # 적용하지 않고 stash에서 제거

# 🌠 stash는 작업 중 다른 브랜치로 이동하거나 임시 보관할 때 유용함

# 6. 특정 커밋만 선택적으로 현재 브랜치에 반영
git cherry-pick abc1234  # abc1234는 가져오고 싶은 커밋 ID

# 🌠 cherry-pick은 &quot;특정 커밋만 골라 적용하고 싶을 때&quot; 사용
# 브랜치 전체를 머지하지 않고, 필요한 변경만 가져오는 데 유리</code></pre>
<p><br /><br /></p>
<hr />
<h2 id="참고자료">참고자료</h2>
<p>코드잇 Git 토픽
<a href="https://www.heropy.dev/p/PcUkdT">Git 핵심 명령어 모음 | heropy.dev</a>
<a href="https://git-scm.com/docs/git-commit#_discussion">Git commit information</a></p>