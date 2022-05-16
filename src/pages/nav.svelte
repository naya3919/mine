<script>
  // isActive: 현재 페이지가 현재 url과 같은지 판별해줌 | 현재페이지를 나타내는 기능을 부여할 때 쓰기좋음
  import { url, isActive } from "@sveltech/routify";

  let id = 12;

</script>

<nav class="menu-box">
  <a href="{$url('/index')}" class="btn" class:located={ $isActive('/index') }>Home</a>
  <a href="{$url('/calculator')}" class="btn" class:located={ $isActive('/calculator') }>장비계산기</a>
</nav>

<style>
  .located {
    border-bottom: 2px solid #005EFF;
  }
</style>