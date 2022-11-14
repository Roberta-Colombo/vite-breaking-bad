<template>
  <div class="my-card text-center">
    <img class="img-fluid" :src="character.img" :alt="character.name" />
    <div class="name">{{ character.name }}</div>
    <div class="caption category">{{ character.category }}</div>
    <div class="caption status">{{ character.status }}</div>
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

.name {
  text-transform: uppercase;
  color: $white;
  font-weight: bold;
  margin-top: 15px;
}

.caption {
  color: $grey;
}

.category {
  margin-top: 18px;
  font-size: 1.2rem;
}

.status {
  margin-bottom: 1rem;
}

.my-card {
  background-color: $bluegray;
  padding: 1rem;
  height: 100%;
}

img {
  height: 250px;
  width: 250px;
  object-position: center;
  object-fit: cover;
}
</style>
