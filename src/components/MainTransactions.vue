<template>
  <div class="MainTransactions">
    <div  class="CurrencyIcon">
      <img :src="require('@/assets/' + imgSrc + '.svg')">
    </div>
    <div class="CurrencyInfos">
      <p> {{ CurrencyTitle }}</p>
      <span> {{ CurrencyAcronym }}</span>
    </div>
    <div class="CurrencyCap">
      <p>Market Cap</p>
      <span :style="{ color: CapValueColor }"> {{ CurrencyCapValue }}</span>
    </div>
    <div class="CurrencyChange">
      <p>24h change</p>
      <span :style="{ color: ChangeValueColor }"> {{ CurrencyChangeValue }}</span>
    </div>
    <div class="CurrencyCurve">
      <img :src="require('@/assets/' + CurrencyCurve + '.svg')">
    </div>
    <div class="CurrencyTrade">
      <button>Trade</button>
    </div>

  </div>
</template>

<script>
export default {
  name: "MainTransactions",
  props: [
    'imgSrc',
    'CurrencyTitle',
    'CurrencyAcronym',
    'CapValueColor',
    'CurrencyCapValue',
    'ChangeValueColor',
    'CurrencyChangeValue',
    'CurrencyCurve',
  ]
}
</script>

<style scoped lang="scss">
.MainTransactions{
  display: flex;
  flex-direction: row;
  justify-content: center;

  padding-top: 0.5rem;
  padding-bottom: 0.5rem;
  margin-bottom: 1rem;

  font-size: 15px;
  font-family: Poppins;
  font-weight: 600;

  background-color: #20232BB2;
  border-radius: 25px;
  span {
    opacity: 70%;
  }
  .CurrencyIcon{
    display: flex;
    vertical-align: middle;
    align-items: center;
    width: 37px;
    object-fit: contain;
    padding-right: 4.5rem;
  }
  .CurrencyInfos {
    display: flex;
    flex-direction: column;
    width: 6.5rem;
  }
  .CurrencyCap{
    display: flex;
    flex-direction: column;
    width: 8rem;

  }
  .CurrencyChange{
    display: flex;
    flex-direction: column;
    width: 8rem;

  }

  .CurrencyCurve{
    width: 143px;
    display: flex;
    vertical-align: middle;
    align-items: center;
    object-fit: contain;

    img{
      width: 143px;
    }

  }
  .CurrencyTrade{
    width: 10rem;
    display: flex;
    justify-content: center;
    vertical-align: middle;
    align-items: center;

    button{
      background: #0D0C0C;
      color: white;
      border: none;

      height: 39px;
      width: 85px;
      left: 1188px;
      top: 974px;
      border-radius: 30px;


      font-family: Poppins;
      font-size: 12px;
      font-weight: 600;
      line-height: 21px;
      letter-spacing: 0em;

    }
  }
}



</style>