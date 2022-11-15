<template>
  <div class="d-flex align-items-center">
    <img src="../assets/img/breaking-bad-logo.png" alt="Breaking Bad logo" />
    <h1>Breaking Bad Api</h1>
  </div>
</template>

<script>
export default {
  name: "TitleComponent",
};
</script>

<style lang="scss" scoped>
@use "../assets/styles/partials/variables" as *;

img {
  width: 10%;
}

h1 {
  color: $logogreen;
}
</style>
