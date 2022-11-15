<template>
  <div class="loader" v-if="store.loading">
    <i class="fa-solid fa-flask-vial px-5 fa-beat-fade"></i>
    <i class="fa-solid fa-flask-vial px-5 fa-beat-fade"></i>
    <i class="fa-solid fa-flask-vial px-5 fa-beat-fade"></i>
  </div>
</template>

<script>
import { store } from "../store";

export default {
  name: "LoaderComponent",
  data() {
    return {
      store,
    };
  },
};
</script>

<style lang="scss" scoped>
@use "../assets/styles/partials/variables" as *;

template {
  position: relative;
}

i {
  font-size: 4rem;
  color: $yellow;
}

.loader {
  text-align: center;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>
