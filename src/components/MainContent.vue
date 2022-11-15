<template>
  <div v-if="store.loading">
    <i class="fa-solid fa-flask-vial"></i>
  </div>

  <div class="my-container" v-if="!store.loading">
    <ResultBar />

    <div class="container">
      <div class="row mt-3 row-cols-5 g-4">
        <!-- <div v-for="(item, index) in characters" :key="index"> -->
        <div v-for="(item, index) in store.characterList" :key="index">
          <CardComponent :character="item" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { store } from "../store";
import CardComponent from "./CardComponent.vue";
import ResultBar from "./ResultBar.vue";

export default {
  name: "MainContent",
  components: { CardComponent, ResultBar },
  data() {
    return {
      store,
    };
  },
};
</script>

<style lang="scss" scoped>
@use "../assets/styles/partials/variables" as *;

.my-container {
  background-color: $white;
  color: black;
  padding: 50px 60px;
}
</style>
