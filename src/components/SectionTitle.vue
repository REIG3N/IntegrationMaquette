<template>
<h3>{{ SectionTitle }}</h3>
</template>

<script>
export default {
  name: "SectionTitle",
  props: [
      'SectionTitle'
  ]
}
</script>

<style scoped lang="scss">
h3{
  font-family: Poppins;
  font-weight: bold;
  font-size: 17px;
  line-height: 33px;
  padding-left: 1rem;
  padding-top: 2rem;
  padding-bottom: 0.75rem;
}
</style>