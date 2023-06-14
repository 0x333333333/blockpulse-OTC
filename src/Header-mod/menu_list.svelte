<script lang="ts">

  export let page = 1;

</script>

<div class="list">
  <p on:click={()=>{page=1;}}>Home</p>
  <p on:click={()=>{page=2;}}>Swap</p>
</div>




<style>

.list {
  position: fixed;
  top: 60px;
  left: 40px;
  width: 100%;
  gap: 30px;
  z-index: 9999;
  display: flex; /* 將容器設置為 Flexbox 佈局 */
}

.list p:hover {
  cursor: pointer;
}

</style>