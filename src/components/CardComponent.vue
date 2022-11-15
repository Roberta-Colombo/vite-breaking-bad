<template>
  <div class="my-card text-center">
    <div class="card-img">
      <div class="overlay"></div>
      <img class="img-fluid" :src="character.img" :alt="character.name" />
    </div>
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
  color: $logogreen;
}

.category {
  margin-top: 18px;
  font-size: 1.2rem;
}

.status {
  margin-bottom: 1rem;
}

.my-card {
  background-color: $lightgreen;
  padding: 1rem;
  height: 100%;
}

img {
  height: 250px;
  width: 250px;
  object-position: center;
  object-fit: cover;
}

.card-img {
  position: relative;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: $yellow-trans;
  display: none;
}

.card-img:hover .overlay {
  display: block;
}
</style>
