<template>
<div class="SideTransactions">
  <img :src="require('@/assets/' + imgSrc + '.svg')" class="CurrencyIcon">
  <div class="CurrencyInfos">
    <p> {{ CurrencyTitle }}</p>
    <span> {{ CurrencyStatus }}</span>
  </div>
  <div class="CurrencyStats">
    <p :style="{ color: ValueColor }"> {{ CurrencyValue }}</p>
    <span> {{ CurrencyDateTime }}</span>
  </div>
</div>

</template>

<script>
export default {
  name: "SideTransactions",
  props: [
      'imgSrc',
      'CurrencyTitle',
      'CurrencyStatus',
      'CurrencyValue',
      'ValueColor',
      'CurrencyDateTime',
      ]
}
</script>

<style scoped lang="scss">

.SideTransactions{
  display: flex;
  flex-direction: row;
  padding-left: 1.25rem;
  padding-bottom: 1rem;
  justify-content: center;

  font-size: 15px;
  font-family: Poppins;
  font-weight: 600
;
  span{
    opacity: 70%;
  }

  img{
    display: flex;
    vertical-align: middle;
    align-items: center;
    width: 37px;
    object-fit: contain;
  }

  .CurrencyInfos {
    display: flex;
    flex-direction: column;
    padding-left: 1.25rem;
    width: 10rem;
  }
  .CurrencyStats{
    width: 10rem;
    display: flex;
    flex-direction: column;
    padding-left: 1rem;

  }
}



</style>