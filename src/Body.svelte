<script>
  import RAQ from './Body-mod/read-and-quote.svelte'
  import LAND from './Body-mod/landing_page.svelte'
  let page = 1;

</script>

<div class="list">
  <p class:active={page === 1} on:click={() => { page = 1; }}>Home</p>
  <p class:active={page === 2} on:click={() => { page = 2; }}>Swap</p>
</div>



{#if page===1 }
  <LAND/>
{:else if page===2 }
  <RAQ/>
{/if}



<style>
  .list {
    position: fixed;
    top: 68px;
    left: 40px;
    width: 100%;
    gap: 30px;
    z-index: 9999;
    display: flex;
    background-color: #242526;
  }

  .list p:hover {
    cursor: pointer;
    filter: drop-shadow(0 0 0.68em #8CFFFBaa);
  }

  .active {
    color: white;
  }
</style>
