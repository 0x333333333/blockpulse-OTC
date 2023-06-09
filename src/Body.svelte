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
    background-color: #f2f2f2;
  }

  .select {
    width: 120px;
    padding: 8px;
    background-color: white;
    border-radius: 4px;
    border: 1px solid #ccc;
  }

  .input {
    width: 80px;
    padding: 8px;
    background-color: white;
    border-radius: 4px;
    border: 1px solid #ccc;
  }
</style>

<div class="container">
  <div class="select">
    <select bind:value={selectedOption1}>
      {#each options as option}
        <option value={option}>{option}</option>
      {/each}
    </select>
  </div>

  <span>X</span>

  <div class="select">
    <select bind:value={selectedOption2}>
      {#each options as option}
        <option value={option}>{option}</option>
      {/each}
    </select>
  </div>

  <span>with</span>

  <input class="input" type="number" bind:value={inputValue1} />

  <div class="select">
    <select bind:value={selectedOption2}>
      {#each options as option}
        <option value={option}>{option}</option>
      {/each}
    </select>
  </div>

  <span>with</span>

  <input class="input" type="number" bind:value={inputValue2} />
</div>