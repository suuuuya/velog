<h2 id="✅-터미널terminal이란">✅ 터미널(Terminal)이란?</h2>
<blockquote>
<p>터미널은 <strong>인풋을 받고, 아웃풋을 출력해 주는 프로그램</strong></p>
</blockquote>
<p>명령어를 입력하고 결과를 확인하는 입출력 인터페이스. 
우리가 흔히 보는 커맨드를 입력하는 검은 화면을 터미널이라고 한다.
<br /><br /></p>
<h2 id="✅-shell-bash-그리고-zsh">✅ shell, bash 그리고 zsh</h2>
<h3 id="shell">shell</h3>
<blockquote>
<p>shell은 <strong>커맨드를 해석해 주는 프로그램</strong>이다.</p>
</blockquote>
<pre><code class="language-html">e.g.)

suya@DESKTOP-3LNI33K:~$ date
Mon Jun 16 21:24:34 KST 2025
suya@DESKTOP-3LNI33K:~$ cal 10 2020
    October 2021
Su Mo Tu We Th Fr Sa
             1  2  3
4  5  6  7  8  9  10
...</code></pre>
<p>컴퓨터는 <code>date</code> 커맨드나 <code>cal</code> 커맨드 같은 단어를 이해하지 못한다. </p>
<p>이런 커맨드들을 컴퓨터가 이해할 수 있는 형태로 바꿔줘야 하는데, 그게 바로 <code>shell</code>이 하는 역할. <code>shell</code>이 커맨드를 컴퓨터가 이해할 수 있는 형태로 바꿔서 전달해 주면, 컴퓨터가 실제로 커맨드를 '실행'하고 결과를 되돌려 준다.</p>
<p><code>shell</code>은 여러 종류가 있고, 종류에 따라 커맨드를 해석하는 방식이나 제공하는 인터페이스가 조금은 다를 수 있지만 대부분의 경우 아주 비슷하거나 똑같이 작동한다.</p>
<h4 id="bash">bash</h4>
<p><code>shell</code> 종류 중 하나가 바로 <strong>bash(Bourne again shell)</strong>. </p>
<p>가장 보편적이고, 많은 유닉스 운영 체제에서 기본 <code>shell</code>로 사용된다. (우분투의 기본 shell)
macOS는 10.15 Catalina 이전 버전에는 <code>bash</code>를 기본으로 썼었는데, 10.15 버전 이후부터는 <code>zsh</code>(Z shell)을 기본으로 쓰기 시작한다.</p>
<p>🌠** <code>shell</code>과 <code>터미널</code>은 엄밀히 말하면 서로 다르지만, 커맨드를 입력하는 검은 화면을 그냥 통상적으로 shell이라고 부르는 경우도 많다고 한다.**
<br /><br /></p>
<h2 id="✅-커맨드의-기본-형태">✅ 커맨드의 기본 형태</h2>
<p>예제로 예시를 들어, 커맨드의 기본 형태에 대해 알아보자.
<br />
특정 년도의 특정 월을 출력해보자.</p>
<pre><code class="language-html">e.g.)
&lt;!-- 2020년 10월 달력 출력--&gt;
suya@DESKTOP-3LNI33K:~$ cal 10 2020
    October 2021
Su Mo Tu We Th Fr Sa
             1  2  3
4  5  6  7  8  9  10
...</code></pre>
<p>어느 대상에 대해 커맨드를 실행할지를 정해주는 것을 <code>아규먼트(argument)</code>또는 <code>인자</code>라고 한다.
커맨드에는 <code>아규먼트</code>를 줄 수도 있고 <code>옵션</code>을 줄 수도 있으며, 옵션을 통해 커맨드가 실행되는 방식을 바꿀 수도 있다.</p>
<p><strong>🌠 용어 정리</strong> </p>
<ul>
<li><code><strong>아규먼트(argument)</strong></code>: 커맨드를 어느 대상에 대해 실행할 것인지 정하는 것</li>
<li><code><strong>옵션(option)</strong></code>: 커맨드를 정확히 어떻게 실행할 것인지 정하는 것<br />
```html
<!-- 아래는 cal 커맨드를 2020년도 10월에 대해 실행한 것. -->
~$ cal 10 2020
=> cal(대상) 10 2020
```
<br />

</li>
</ul>
<p>옵션 <code>-</code>와 특정 알파벳을 쓴다.</p>
<pre><code class="language-html">~$ cal -j
         Jun 2025
Su   Mo  Tu  We  Th  Fr  Sa
152 153 154 155 156 157 158 
...

~$ cal -y

출력
...</code></pre>
<p>옵션은 붙여 사용하면된다.</p>
<pre><code class="language-html">~$ cal -yj

출력
...</code></pre>
<p> 🌠** 옵션을 외울 필요는 없고 커맨드의 기본 형태와 커맨드 옵션 아큐먼트에 대해 기억하기**</p>
<p> <br /><br /></p>
<h2 id="✅-커맨드-매뉴얼--man">✅ 커맨드 매뉴얼 : man</h2>
<p> 유닉스 커맨드에 대한 공식 매뉴얼이 있다. 공식 매뉴얼도 커맨드로 읽어볼 수 있다.
<code>man [검색해 볼 커맨드]</code></p>
<p><strong>*&nbsp;매뉴얼 나가기</strong> : <code>q</code></p>
<pre><code class="language-html">e.g.)

~$ man cal

출력
...

NAME
       cal, ncal — displays a calendar and the date of Easter

SYNOPSIS
       cal [-3hjy] [-A number] [-B number] [[month] year]
       cal [-3hj] [-A number] [-B number] -m month [year]
       ncal [-3bhjJpwySM] [-A number] [-B number] [-W number] [-s country_code] [[month] year]
       ncal [-Jeo] [-A number] [-B number] [year]
       ncal [-CN] [-H yyyy-mm-dd] [-d yyyy-mm]

DESCRIPTION
       The  cal  utility  displays  a simple calendar in traditional format and ncal offers an alternative layout,
       more options and the date of Easter.  The new format is a little cramped but it makes a year fit on a 25x80
       terminal.  If arguments are not specified, the current month is displayed.

       The options are as follows:

       -h      Turns off highlighting of today.

       -J      Display Julian Calendar, if combined with the -o option, display date of Orthodox Easter  according
               to the Julian Calendar.
... </code></pre>
<ul>
<li><code><strong>NAME</strong></code> : 커맨드의 이름과 커맨드가 무엇을 하는지에 대한 간단한 설명</li>
<li><code><strong>SYNOPSIS</strong></code> : 커맨드의 문법, 쓸 수 있는 옵션과 아규먼트 정리
[] 대괄호로 감싸져 있는 건 필수가 아니고 옵셔널하다는 의미. 사용의 선택 사항을 뜻한다.</li>
<li>가 붙은 것들은 옵션, 아닌 것은 아규먼트</li>
<li><code><strong>DESCRIPTION</strong></code> : 검색한 커맨트에 대한 일반적인 설명이다. 각 옵션에 대한 설명도 읽어볼 수 있다.</li>
<li>이 외 해당 커맨드와 비슷한 커맨드들, 참고할 만한 정보, 유의사항이 작성되어있다.<br />

</li>
</ul>
<p>위의 매뉴얼을 활용해서 아래와 같은 기능을 만들어봤다.</p>
<pre><code class="language-html">&lt;!-- 지금으로부터 3개월 전, 3개월 후의 달력을 출력 --&gt;
cal [-3hjy] [-A number] [-B number] [[month] year]

==&gt; ~$ cal -B 3 -A 3

출력
...</code></pre>
<p><img alt="" src="https://velog.velcdn.com/images/iamsuuya/post/5742b704-7746-4542-b19a-c871a3369bea/image.png" />
<br /></p>
<h2 id="✅-터미널-사용-꿀팁">✅ 터미널 사용 꿀팁</h2>
<p>** 1. 위쪽 방향 키**
 전에 실행했던 커맨드를 재실행 해야하는 경우가 많다.
 위쪽 방향 키를 계속 클릭하면 전에 실행했던 커맨드 입력된다.</p>
<p>** 2. 커서 이동**
 커맨드를 잘못 입력했을 때
  -&nbsp;줄 가장 앞으로 이동: <code>Ctrl</code> + <code>A</code>
  -&nbsp;줄 가장 뒤로 이동: <code>Ctrl</code> + <code>E</code></p>
<p> 단어 단위 커서 이동 
 -&nbsp;Windows: <code>Alt</code> + <code><-</code>, <code>Alt</code> + <code>-></code>
 -&nbsp;Mac OS: <code>Option</code> + <code><-</code>, <code>Option</code> + <code>-></code></p>
<p>** 3. Ctrl + C**
 실행하고 있는 작업을 취소할 때 사용하면 새로운 프롬프트가 뜨고,
  커맨드가 실행되는 도중에 사용하면 작업이 종료된다.</p>
<p>**  4. clear 커맨드**
  커맨드를 계속 실행하면 화면이 지저분해지고, 프롬프트가 터미널 가장 아래 부분에 있어서 보기가 불편하다.
  <code>clear</code>는 터미널 내용을 지워서 깨끗하게 만들어준다. 내용만 지워주기 때문에 히스토리는 남아 있다.</p>
<p> ** 5. 탭 키**
  <code>Tab</code> 키를 누르면 작성하고 있는 커맨드나 아규먼트를 자동 완성해준다.
  e.g.) unc + <code>Tab</code> 클릭 -&gt; <code>uncompress</code> 커맨드 자동 완성
  더 짧게 'un'으로 입력하면 un으로 시작하는 모든 옵션들을 보여준다.</p>
<p> <br /><br /></p>
<hr />
<h2 id="참고자료">참고자료</h2>
<p>코드잇 &lt;유닉스 커맨드 시작하기&gt; 토픽
<a href="https://www.google.com/search">https://www.google.com/search</a>
<a href="https://inpa.tistory.com/entry/LINUX-%F0%9F%93%9A-%EC%8B%9C%EA%B0%84%EC%9D%84-%EC%A0%88%EC%95%BD%ED%95%98%EB%8A%94-%ED%84%B0%EB%AF%B8%EB%84%90-%EB%8B%A8%EC%B6%95%ED%82%A4-Command-Line-Tip">https://inpa.tistory.com/entry/LINUX-%F0%9F%93%9A-%EC%8B%9C%EA%B0%84%EC%9D%84-%EC%A0%88%EC%95%BD%ED%95%98%EB%8A%94-%ED%84%B0%EB%AF%B8%EB%84%90-%EB%8B%A8%EC%B6%95%ED%82%A4-Command-Line-Tip</a></p>