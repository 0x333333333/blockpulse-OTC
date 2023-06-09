<script>
  let options = ['BTC', 'ETH', 'USDT', 'HKD', 'USD'];
  let selectedOption1 = options[0];
  let selectedOption2 = options[0];
  let inputValue1 = '';
  let inputValue2 = '';
</script>

<style>
  .container {
    display: flex;
    align-items: center;
    gap: 16px;
    padding: 16px;
    background-color: #006590;
    border-radius: 14px;
  }

  .select {
    height: 30px;
    flex: 1;
  }

  .select select {
    width: 100%;
    height: 100%;
    padding: 8px;
    background-color: white;
    border-radius: 4px;
    border: 1px solid #ccc;
  }

  .input {
    height: 30px;
    flex: 1;
    width: 100%;
    height: 100%;
    padding: 5px;
    background-color: white;
    border-radius: 4px;
    border: 1px solid #ccc;
  }


  .grey {
  color : #444444;
  }
</style>




<div class="container">

<div class="top-section">

  <p>BUY</p>

  <input class="input" type="number" bind:value={inputValue1} />

  <div class="select">
    <select bind:value={selectedOption1}>
      {#each options as option}
        <option value={option}>{option}</option>
      {/each}
    </select>
  </div>
</div>


<div class="bottom-section">
  <p class="grey">WITH</p>

  <input class="input" type="number" bind:value={inputValue2} />

  <div class="select">
    <select bind:value={selectedOption2}>
      {#each options as option}
        <option value={option}>{option}</option>
      {/each}
    </select>
  </div>
  </div>

</div>