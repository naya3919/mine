<script>
  import { onMount } from 'svelte';
  import { goto } from '@sveltech/routify';
  // your script goes here

  onMount(() => {
    // 해당 페이지 진입 시 메인으로 보냄
    setTimeout(() => {
      $goto('/index');
    }, 1000);
  });
</script>

<p>해당 페이지는 없는 페이지입니다</p>
<p>404 Not Found Page</p>
<p>1초 뒤 메인페이지로 이동합니다.</p>