<template>
  <img :src="require('@/assets/' + imgSrc + '.svg')" class="SideIcons">
</template>

<script>
export default {
  name: "SideIcons",
  props: [
    'imgSrc'
  ]
}
</script>

<style scoped lang="scss">
img{
  width: 38px;
  height: 38px;

}
</style>