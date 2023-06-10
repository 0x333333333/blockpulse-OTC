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

  .big-container {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    padding: 0.6em;
    border: 1px solid #8CFFFB;
    border-radius: 14px;
  }
  .container {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    width: 100%;
    gap: 0.1em;
    padding: 0.3em;
    border-radius: 14px;
  }

  .select {
    flex: 1;
    max-width: 300px;
    height: 1.6em;
    padding: 0.1em;
  }

  .select select {
    width: 100%;
    height: 100%;
    padding: 4px;
    background-color: rgba(140, 255, 251, 0.1);
    border-radius: 4px;
    border: 1px solid #444444;
    color: white;
    transition: background-color 0.25s;
  }
  select:hover {
    font-weight: bold;
    color: #242526;
    background-color: rgba(140, 255, 251, 0.9);
    filter: drop-shadow(0 0 1em #8CFFFBaa)
  }
  .input {
    flex: 1;
    width: 39px;
    height: 1.6em;
    background-color: rgba(140, 255, 251, 0.1);
    border-radius: 4px;
    border: 1px solid #444444;
    color: white;
    text-align: center;
    transition: background-color 0.25s;
  }
  input:hover {
    font-weight: bold;
    color: #242526;
    background-color: rgba(140, 255, 251, 0.9);
    filter: drop-shadow(0 0 1em #8CFFFBaa)
  }
  .grey {
    color: #444444;
  }
  .white {
    color: #ffffff;
    font-size: 16px;
  }
</style>


<div class="big-container">


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
  </div></div>


<div class="container">
  <p class="white">WITH</p>

  <div class="select">
    <select bind:value={selectedOption2}>
      {#each fiat as option}
        <option value={option}>{option}</option>
      {/each}
    </select>
  </div>

  <p class="white">BY NOW</p>

</div>

<br><button>Quote</button>

</div>
