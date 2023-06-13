<script>
  import { onMount } from 'svelte';
  import { fade } from 'svelte/transition';

  let act =  ['BUY', 'SELL'];
  let fiat = ['HKD', 'USD'];
  let crypto = ['BTC', 'ETH', 'USDT'];

  let actOption = act[0];  
  let fiatOption = fiat[0];
  let cryptoOption = crypto[0];
  let inputValue = '';
  let outputValue = '';

  let BTCask = 0;
  let BTCbid = 0;
  let ETHask = 0;
  let ETHbid = 0;

  let showNewContainer = false;
  let countdown = 30;
  let countdownInterval;

  function createNewContainer() {
    showNewContainer = true;

    countdown = 30;
    countdownInterval = setInterval(() => {
      countdown--;
      if (countdown === 0) {
        clearInterval(countdownInterval);
        showNewContainer = false;
      }
    }, 1000);
  }
  

  async function fetchBTC() {
    const response = await fetch('https://api.bybit.com/v5/market/orderbook?category=spot&limit=1&symbol=BTCUSDT');
    const data = await response.json();
    if (data.retCode === 0) {
      BTCask = parseFloat(data.result.a[0][0]);
      BTCbid = parseFloat(data.result.b[0][0]);
    }
  }
  async function fetchETH() {
    const response = await fetch('https://api.bybit.com/v5/market/orderbook?category=spot&limit=1&symbol=ETHUSDT');
    const data = await response.json();
    if (data.retCode === 0) {
      ETHask = parseFloat(data.result.a[0][0]);
      ETHbid = parseFloat(data.result.b[0][0]);
    }
  }

  onMount(() => {
    fetchBTC(); fetchETH();// 初始化数据
    const interval = setInterval(() => {fetchBTC();}, 5000); // 5秒更新
    const interval1 = setInterval(() => {fetchETH();}, 5000);
    return () => {
      clearInterval(interval);
      clearInterval(interval1);
    };
  });
  
</script>

<style>
.container-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 0px;
}
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

.new-container {
  animation: fade 0.4s;
  transition: opacity 0.4s;
  margin-top: 1em;
  text-align: center;
}

.content {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.select {
  flex: 1;
  max-width: 300px;
  height: 1.6em;
  padding: 0.1em;
  text-align: center;
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
  text-align: center;
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


@keyframes fade {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>




{#if showNewContainer}

  <div class="big-container"><div class="content">
    <h3>Buying X BTC with Y HKD</h3>
    <p>Countdown: {countdown}s</p>
    <button class="execute-button" on:click={createNewContainer}>Execute</button> <br>
    <button class="execute-button" on:click={() => {showNewContainer = false;}}>Cancel</button>
  </div></div>

{:else}

  <div class="container-wrapper">

  <div class="big-container">

  <div class="container">

  <div class="select">
    <select bind:value={actOption}>
      {#each act as option}
        <option value={option}>{option}</option>
      {/each}
    </select>
  </div>

  <input class="input" type="number" bind:value={inputValue} />

  <div class="select">
    <select bind:value={fiatOption}>
      {#each crypto as option}
        <option value={option}>{option}</option>
      {/each}
    </select>
  </div></div>

  <div class="container">
    <p class="white">WITH</p>
      <div class="select">
        <select bind:value={cryptoOption}>
          {#each fiat as option}
            <option value={option}>{option}</option>
          {/each}
        </select>
      </div>
    <p class="white">BY NOW</p>
  </div>

  <br><button on:click={createNewContainer}>Quote</button></div><br></div>

{/if}




