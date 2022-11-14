<template>
  <div class="text-center">
    <div class="inner-card">
      <img class="img-fluid" :src="character.img" :alt="character.name" />
      <div>{{ character.name }}</div>
      <div>{{ character.category }}</div>
      <div>{{ character.status }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardComponent",
  props: {
    character: Object,
  },
};
</script>

<style lang="scss" scoped>
@use "../assets/styles/partials/variables" as *;
</style>
