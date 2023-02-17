<template>
  <div class="SideAsset" :style="{ color: TextColor, background: BackgroundColor }">
    <div class="CurrencyLogo">
      <img :src="require('@/assets/' + imgSrc + '.svg')">
        <p> {{ CurrencyTitle }}</p>

    </div>
    <div class="CurrencyInfos">
      <p> {{ CurrencyValue }}</p>
      <p> {{ CurrencyAcronym }}</p>
    </div>
  </div>
</template>
<script>
export default {
  name: "SideAsset",
  props: [
    'imgSrc',
    'CurrencyTitle',
    'CurrencyValue',
    'CurrencyAcronym',
    'BackgroundColor',
    'TextColor'
  ]
}
</script>
<style scoped lang="scss">
.SideAsset{
  width: 370px;
  height: 140px;
  border-radius: 30px;
  padding: 1rem 1rem 0.7rem 1rem;
  margin-top: 1rem;
  display: flex;
  flex-direction: column;
  @media (max-width: 1440px) {
    width: 24vw;
  }

  .CurrencyLogo{
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 62px;

    font-family: 'Poppins';
    font-style: normal;
    font-weight: 600;
    font-size: 14px;
    line-height: 23px;
    img{
      display: flex;
      width: 62px;
    }
    .CurrencyName{
      p{

      }
    }
  }
  .CurrencyInfos{
    display: flex;
    padding-right: 20px;
    padding-top: 0.1rem;
    justify-content: space-between;
    align-items: center;
    font-family: 'Poppins';
    font-style: normal;
    font-weight: 600;
    font-size: 19px;
    line-height: 33px;


  }
}
</style>