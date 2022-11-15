<template>
  <div class="result-bar">
    Found {{ store.characterList.length }} characters
  </div>
</template>

<script>
import { store } from "../store";

export default {
  name: "ResultBar",
  data() {
    return {
      store,
    };
  },
};
</script>

<style lang="scss" scoped>
@use "../assets/styles/partials/variables" as *;

.result-bar {
  background-color: $greyblack;
  height: 50px;
  color: $white;
  line-height: 50px;
  font-weight: bold;
  padding-left: 10px;
}
</style>
