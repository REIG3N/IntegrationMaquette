<template>
  <li class="menuLink">
    <img :src="require('@/assets/' + imgTitle + '.svg')" class="menuIcon" >
    <p :style="{ color: TextColor }">{{ imgTitle }}</p>
  </li>
</template>

<script>
export default {
  name: "navbarLink",
  props: [
      'imgTitle',
      'TextColor'
  ]
}
</script>

<style scoped lang="scss">
.menuLink{
  display: flex;
  align-items: center;
  opacity: 80%;
  width: 9rem;
  padding-left: 0.5rem;
  @media (max-width: 890px) {
    color: white;
  }
  img{
    width: 30px;
    height: 30px;
  }
  p{
    padding: 1rem;
    font-size: 17px;
    font-weight: 500;
    font-family: Poppins;
    @media (max-width: 890px) {
      opacity: 0%;
      font-size: 10px;
    }

  }
}
</style>