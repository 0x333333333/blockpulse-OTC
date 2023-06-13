<script>
  import BP_logo from '../assets/blockpulse.svelte';
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
  background-color: #242526;
}

.header-content {
  display: flex;
  align-items: center;
  padding: 0 16px; /* 或者根據你的設計設置適當的內邊距 */
}

.logo {
  margin-right: 8px;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 1em #8CFFFBaa);
}
.logo.svelte:hover {
  filter: drop-shadow(0 0 1em #8CFFFBaa);
}

.company-name {
  margin: 0;
  font-size: 1.1em; /* 或者根據你的設計設置適當的字體大小 */
}

.grey {
  color : rgba(140, 255, 251, 0.3);
}

</style>



<header class={isFixed ? 'header fixed' : 'header'}>
  <div class="header-content">
    <div class="logo">
      <BP_logo/>
    </div>
  </div>
  <p class="grey">Zero fees. Tight spreads. Fast settlement.</p>

</header>
