<script>
  import BP_logo from './assets/blockpulse.svelte';
  import { onMount } from 'svelte';

  let isFixed = false;

  onMount(() => {
    window.addEventListener('scroll', handleScroll);
  });

  function handleScroll() {
    const scrollTop = window.pageYOffset || document.documentElement.scrollTop;
    isFixed = scrollTop > 0;
  }

</script>

<style>
  .header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    padding: 10px;
    z-index: 9999;
  }

.header-content {
  display: flex;
  align-items: center;
  padding: 0 16px; /* 或者根據你的設計設置適當的內邊距 */
}

.logo {
  margin-right: 8px; /* 或者根據你的設計設置適當的右邊距 */
}

.company-name {
  margin: 0;
  font-size: 1.1em; /* 或者根據你的設計設置適當的字體大小 */
}

</style>

<header class={isFixed ? 'header fixed' : 'header'}>
  <div class="header-content">
    <div class="logo">
      <BP_logo/>
    </div>
    <h1 class="company-name">Blockpulse OTC</h1>
  </div>
</header>
