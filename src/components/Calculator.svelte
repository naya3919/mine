<script>
  import constant from "../constant.js"

  let selectValue = [];
  let inputValue = [0, 0, 0, 0];
  let total = 0;

  let grade = '';

  $: if(total == 0) {
    grade = '???';
    } else if (total <= 50) {
      grade = 'D';
    } else if (total >= 51 && total < 61) {
      grade = 'C';
    } else if (total >= 61 && total < 70) {
      grade = 'B';
    } else if (total >= 71 && total < 80) {
      grade = 'A';
    } else if (total >= 80) {
      grade = 'S';
    }

  function run() {
    let sum = 0;
    for (let i = 0; i < inputValue.length; i++) {
      sum = sum + (selectValue[i].baseScore * inputValue[i]);
    }
    total = sum;
  }
</script>

<div class="container">
  {#each Array(4) as _, i}
  <div>
    <select bind:value={selectValue[i]}>
      {#each constant as data}
        <option value={data}>{data.title}</option>
        {/each}
      </select>
      {#if selectValue[i]}
        <input class="score" type="text" readonly bind:value={selectValue[i].baseScore}>
      {/if}
    <input class="score" type="number" bind:value={inputValue[i]}>
  </div>
  {/each}
  <button class="btn" on:click={run}>계산</button>
  <div>재련 후 장비점수 : {total}</div>
  <div>등급 : {grade} 급</div>
</div>

<style>
  .score {
    width: 5em;
  }
  .btn {
    width: 100%
  }
</style>