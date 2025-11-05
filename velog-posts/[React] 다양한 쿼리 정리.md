<h2 id="dependant-query">Dependant Query</h2>
<h4 id="예시">예시</h4>
<blockquote>
<p>첫 번째 쿼리는 유저의 정보를 받아 오고, 두번째 쿼리는 받아온 유저의 정보에서 아이디를 이용해 해당 유저의 프로젝트를 받아오는 상황</p>
</blockquote>
<p>위처럼 만약 어떤 두 쿼리가 의존관계가 있어 어떤 특정 순서대로 실행이 되어야 하는 경우에는 어떻게 해야 할까? 
<br /></p>
<h3 id="dependant-query란">Dependant Query란?</h3>
<p>어떤 특정 값을 먼저 받아오거나 어떤 조건이 되었을 때 쿼리 함수를 실행하려면 <code>useQuery()</code>의 enabled 옵션을 사용할 수 있다.</p>
<p><strong>어떤 특정 값이나 조건이 충족된 이후에 실행되는 쿼리</strong>를 <code>Dependant Query</code>라고 한다.</p>
<pre><code class="language-jsx">const { data: userInfoData } = useQuery({
  queryKey: queryKey,
  queryFn: queryFn,
  enabled: !!username,
});</code></pre>
<br />

<h4 id="paginated-query">Paginated Query</h4>
<p>쿼리 키에 페이지 정보를 포함해서 페이지네이션을 구현할 수 있다.
placeholderData 옵션을 활용하면, 새로운 페이지를 보여줄 때 이전의 데이터를 보여 주다가 새로운 데이터가 오면 자연스럽게 전환할 수 있다.</p>
<pre><code class="language-jsx">const {data: postsData } = useQuery({
    queryKey: ['posts', page],
    queryFn: () =&gt; getPosts(page, PAGE_LIMIT),
    placeholderData: keepPreviousData,
});</code></pre>
<p><code>prefetchQuery()</code> 함수를 사용하면 다음 페이지의 데이터를 미리 fetch하도록 구현할 수도 있다.</p>
<pre><code class="language-jsx">useEffect(() =&gt; {
  if (!isPlaceholderData &amp;&amp; postsData?.hasMore) {
    queryClient.prefetchQuery({
      queryKey: ['posts', page + 1],
      queryFn: () =&gt; getPosts(page + 1, PAGE_LIMIT),
    });
  }
}, [isPlaceholderData, postsData, queryClient, page]);</code></pre>
<br />

<hr />
<br />

<h2 id="infinite-query">Infinite Query</h2>
<p><code>useInfiniteQuery()</code> 훅에서는 page param 값을 활용하여 페이지를 더 불러온다.</p>
<pre><code class="language-jsx">const {
  data: postsData,
  isPending,
  isError,
  hasNextPage,
  fetchNextPage,
  isFetchingNextPage,
} = useInfiniteQuery({
  queryKey: ['posts'],
  queryFn: ({ pageParam }) =&gt; getPosts(pageParam, LIMIT),
  initialPageParam: 0,
  getNextPageParam: (lastPage, allPages, lastPageParam, allPageParams) =&gt;
    lastPage.hasMore ? lastPageParam + 1 : undefined,
});</code></pre>
<p><code>useQuery()</code>에서는 data에 한 페이지에 해당하는 데이터만 담고 있음 <code>useInfiniteQuery()</code>에서는 data에 모든 페이지의 데이터가 pages라는 프로퍼티로 배열에 담겨 있다.</p>
<p><code>getNextPageParam()</code> 함수에서 다음 페이지가 있는 경우 다음 page param 값을 리턴함 
<code>fetchNextPage()</code> 함수에서는 이렇게 리턴된 page param 값을 쿼리 함수로 전달해 다음 페이지의 데이터를 받아온다.</p>
<br />

<hr />
<br />

<h2 id="optimistic-updates">Optimistic updates</h2>
<h3 id="옵티미스틱-업데이트란">옵티미스틱 업데이트란?</h3>
<blockquote>
<p>옵티미스틱 업데이트는 좋아요 기능과 같이 유저에게 빠른 피드백을 제공해야 하는 경우에 사용합니다. 간단히 말하자면 <strong>서버로부터의 리스폰스를 기다리지 않고 유저에게 바로 낙관적인 피드백을 주는 것이 옵티미스틱 업데이트</strong>인데요. 
서버가 제대로 동작하는 걸 낙관적으로 기대하는 것이죠. 예를 들어 '좋아요' 버튼을 눌렀을 때 실제로 서버에 반영이 제대로 되었는지를 확인하지 않고 유저에게 바로 '좋아요' 버튼을 누른 것처럼 버튼을 활성화해서 보여주는 거죠.
-코드잇 토픽</p>
</blockquote>
<p>Optimistic updates는 서버가 제대로 동작할 것을 낙관적으로 기대하며, 서버로부터의 리스폰스를 기다리지 않고 유저에게 바로 피드백을 주는 방식을 말한다.</p>
<p>리액트 쿼리의 훅들을 이용해 옵티미스틱 업데이트로 좋아요 기능을 구현해 할 수 있는데, useMutation()의 onMutate, onError, onSettled 옵션을 활용해 Optimistic updates를 구현할 수 있다.</p>
<pre><code class="language-jsx">const likeMutation = useMutation({
  mutationFn: async ({ postId, username, userAction }) =&gt; {
    if (userAction === USER_ACTION.LIKE_POST) {
      await likePost(postId, username);
    } else {
      await unlikePost(postId, username);
    }
  },
  onMutate: async ({ postId, username, userAction }) =&gt; {
    await queryClient.cancelQueries({
      queryKey: [QUERY_KEYS.LIKE_STATUS, postId],
    });
    await queryClient.cancelQueries({
      queryKey: [QUERY_KEYS.NUM_OF_LIKES, postId],
    });

    const prevLikeStatus = queryClient.getQueryData([
      QUERY_KEYS.LIKE_STATUS,
      postId,
      username,
    ]);
    const prevLikeCount = queryClient.getQueryData([
      QUERY_KEYS.LIKE_COUNT,
      postId,
    ]);

    queryClient.setQueryData(
      [QUERY_KEYS.LIKE_STATUS, postId, username],
      () =&gt; userAction === USER_ACTION.LIKE_POST
    );
    queryClient.setQueryData([QUERY_KEYS.LIKE_COUNT, postId], (prev) =&gt; {
      userAction === USER_ACTION.LIKE_POST ? prev + 1 : prev - 1;
    });

    return { prevLikeStatus, prevLikeCount };
  },
  onError: (err, { postId, username }, context) =&gt; {
    queryClient.setQueryData(
      [QUERY_KEYS.LIKE_STATUS, postId, username],
      context.prevLikeStatus
    );
    queryClient.setQueryData(
      [QUERY_KEYS.LIKE_COUNT, postId],
      context.prevLikeCount
    );
  },
  onSettled: (data, err, { postId, username }) =&gt; {
    queryClient.invalidateQueries({
      queryKey: [QUERY_KEYS.LIKE_STATUS, postId, username],
    });
    queryClient.invalidateQueries({
      queryKey: [QUERY_KEYS.LIKE_COUNT, postId],
    });
  },
});</code></pre>
<h4 id="onmutate">onMutate</h4>
<p>옵티미스틱 업데이트를 통해 변경하려고 하는 데이터가 refetch로 인해 덮어씌워지는 것을 막기 위해 <code>cancelQueries()</code>를 실행하여, 좋아요 관련 데이터를 받아 오지 않도록 쿼리를 취소해 준다.</p>
<p>에러가 발생했을 때는 이전의 데이터로 롤백해 줘야 하는데, 롤백용 데이터를 따로 저장해 원하는 값으로 쿼리 데이터를 미리 변경하고 롤백용 데이터를 리턴</p>
<h4 id="onerror">onError</h4>
<p>롤백용 데이터를 세 번째 파라미터인 context로 받아 context 값으로 쿼리 데이터를 변경해 준다.</p>
<h4 id="onsettled">onSettled</h4>
<p>에러 여부와 상관없이 백엔드 서버와 데이터를 동기화해주기 위해 좋아요 관련 데이터 쿼리를 invalidate해 준다.</p>