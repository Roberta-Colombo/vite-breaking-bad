<template>
  <div class="container">
    <div class="wrapper">
      <div class="result-bar">Component Barra risultati</div>

      <div class="row mt-3 row-cols-5">
        <div class="card" v-for="(item, index) in characters" :key="index">
          <CardComponent :character="item" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CardComponent from "./CardComponent.vue";

export default {
  name: "MainContent",
  components: { CardComponent },
  props: ["characters"],
};
</script>

<style lang="scss" scoped>
@use "../assets/styles/partials/variables" as *;

.wrapper {
  background-color: $white;
  color: black;
  padding: 60px 60px;
}

.result-bar {
  background-color: $greyblack;
}

.card {
  background-color: $bluegray;
  padding: 10px;
  margin-bottom: 20px;
}
</style>
