<template>
  <div class="my-container">
    <div class="result-bar">Found {{ characters.length }} characters</div>

    <div class="container">
      <div class="row mt-3 row-cols-5 g-4">
        <div v-for="(item, index) in characters" :key="index">
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

.my-container {
  background-color: $white;
  color: black;
  padding: 50px 60px;
}

.result-bar {
  background-color: $greyblack;
  height: 50px;
  color: $white;
  line-height: 50px;
  font-weight: bold;
  padding-left: 10px;
}
</style>
