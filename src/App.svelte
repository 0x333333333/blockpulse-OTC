<script lang="ts">

  import Header from './Header.svelte'
  import Body from './Body.svelte'
  import LIST from './Header-mod/menu_list.svelte'

  export let page = 1;

</script>


<main>

  <Header/>
  <LIST/>
  <Body/>

</main>


<style>

</style>
