<script>
  let act =  ['BUY', 'SELL'];
  let fiat = ['HKD', 'USD'];
  let crypto = ['BTC', 'ETH', 'USDT'];
  let selectedOption0 = act[0];  
  let selectedOption1 = fiat[0];
  let selectedOption2 = crypto[0];
  let inputValue = '';
  let outputValue = '';
</script>

<style>
  .container {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 16px;
    padding: 16px;
    background-color: #006590;
    border-radius: 14px;
  }

  .select {
    flex: 1;
    max-width: 200px;
    height: 30px;
  }

  .select select {
    width: 68px;
    height: 30px;
    padding: 5px;
    background-color: #006590;
    border-radius: 4px;
    border: 1px solid #444444;
    color: white;
  }

  .input {
    width: 68px;
    max-height: 30px;
    padding: 5px;
    background-color: #006590;
    border-radius: 4px;
    border: 1px solid #444444;
    color: white;
    text-align: center;
  }

  .grey {
    color: #444444;
  }
  .white {
    color: #ffffff;
  }
</style>

<div class="container">

  <div class="select">
    <select bind:value={selectedOption0}>
      {#each act as option}
        <option value={option}>{option}</option>
      {/each}
    </select>
  </div>


  <input class="input" type="number" bind:value={inputValue} />


  <div class="select">
    <select bind:value={selectedOption1}>
      {#each crypto as option}
        <option value={option}>{option}</option>
      {/each}
    </select>
  </div>

  <p class="white">WITH</p>

  <div class="select">
    <select bind:value={selectedOption2}>
      {#each fiat as option}
        <option value={option}>{option}</option>
      {/each}
    </select>
  </div>
</div>
