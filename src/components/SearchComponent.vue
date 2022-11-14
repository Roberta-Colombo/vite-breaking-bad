<template>
  <div class="my-container">
    <button class="select-cat">
      Select category<i class="fa-solid fa-angle-down ms-2"></i>
    </button>
  </div>
</template>

<script>
export default {
  name: "SearchComponent",
};
</script>

<style lang="scss" scoped>
@use "../assets/styles/partials/variables" as *;

.select-cat {
  margin-left: 10px;
  background-color: $white;
  color: black;
  margin-top: 45px;
  margin-bottom: 20px;
  padding: 6px 9px;
  border-radius: 5px;
  border-style: none;
}
</style>
