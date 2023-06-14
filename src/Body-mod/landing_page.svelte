<script>
  import Money from '../lib/money.svelte'
  import Rate from '../lib/rate.svelte'
  let TT1 = false;
  let TT2 = false;

</script>

<style>
.tooltip {
  position: absolute;
  top: calc(100% + 5px);
  left: 50%;
  transform: translateX(-50%);
  color: #fff;
  padding: 5px;
  border-radius: 4px;
  font-size: 0.8em;
}

.big-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 90px;
}
.container-wrapper {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 120px; /* 調整容器的寬度 */
  height: 120px; /* 調整容器的高度 */
}

.container svg {
  width: 100px; /* 調整 SVG 的寬度 */
  height: 100px; /* 調整 SVG 的高度 */
}

.container p {
  margin-top: 10px; /* 調整文字與 SVG 的間距 */
  font-size: 16px; /* 調整文字的字體大小 */
  text-align: center; /* 將文字置中 */
}
.small_white {
  color: white;
  font-size: 0.8em;
}
p:hover {
  filter: drop-shadow(0 0 1em #8CFFFBaa)
}
</style>

<div class="big-wrapper">
<p>🌐 BlockPul​​se 場外交易🌐</p>
<p>➖➖➖➖➖➖➖➖➖➖➖➖➖</p>
<p>💼歡迎來到更順暢的交易體驗💼</p>
<p class="small_white">通過 BlockPul​​se OTC 擁抱加密交易的未來。享受實體場所交易的便利和安全。</p><br>
<button>🚀 開始 ➜</button>
<p>➖➖➖➖➖➖➖➖➖➖➖➖➖</p>
<p>💡我們的服務💡</p> <br>

<!-- <p>探索我們專為您的終極加密貨幣交易體驗而設計的服務。</p> -->
<div class="container" on:mouseenter={() => (TT1 = true)}
  on:mouseleave={() => (TT1 = false)}> <Money/> <br> 港幣現金交易
  {#if TT1} <div class="tooltip">訪問我們在香港的實際位置以進行安全的面對面交易</div> {/if}
</div>
<div class="container" on:mouseenter={() => (TT2 = true)}
  on:mouseleave={() => (TT2 = false)}> <Rate/> <br> 實時匯率
  {#if TT2} <div class="tooltip">訪問我們在香港的實際位置以進行安全的面對面交易</div> {/if}
</div>


<p>2. 📈實時匯率
<p>隨時了解最準確和實時的加密貨幣匯率。了解更多 ➜
<p>3. 🛠️場外交易儀錶盤
<p>全面且用戶友好的交易儀表板，可實現高效交易。了解更多 ➜
<p>4. 📝詢價報價系統
<p>為您的交易請求接收實時準確的報價。了解更多 ➜
<p>5. 🎁推薦計劃
<p>邀請您的朋友使用 BlockPul​​se OTC 進行交易並獲得獎勵以及高達 30% 的現金或加密佣金。了解更多 ➜
➖➖➖➖➖➖➖➖➖➖➖➖➖
📚關於我們📚
在 BlockPul​​se OTC，我們的使命是讓每個人都能交易加密貨幣，提供世界一流的 OTC 交易體驗。閱讀更多 ➜
➖➖➖➖➖➖➖➖➖➖➖➖➖
🎈加密交易新手？🎈
通過我們的分步指南和全面的常見問題解答，了解如何開始您的旅程。了解更多 ➜
➖➖➖➖➖➖➖➖➖➖➖➖➖
🔍安全合規的交易🔍
憑藉強大的 KYC/AML 合規性，我們確保了一個安全且值得信賴的交易平台。了解更多 ➖➜
➖➖➖➖➖➖➖➖➖➖➖➖➖
📞聯繫我們📞
我們是來幫忙的。
* 電話：xxx-xxxx-xxxx
* 郵箱：info@blockpulseotc.com
* 地點：香港上環
* 聯絡我們 ➜
➖➖➖➖➖➖➖➖➖➖➖➖➖
🔗快速鏈接🔗
* 常見問題
* 條款和條件
* 隱私政策
* 反洗錢/KYC 政策
➖➖➖➖➖➖➖➖➖➖➖➖➖
©️ 2023 BlockPul​​se 場外交易中心。版權所有。

</div>