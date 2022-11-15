<template>
  <div class="my-container">
    <form
      class="d-flex justify-content-start align-items-center"
      @submit.prevent="searchCharacters"
    >
      <!-- <button class="select-cat">
      Select category<i class="fa-solid fa-angle-down ms-2"></i>
    </button> -->
      <label class="me-3" for="category">
        <strong>Filter by series:</strong>
      </label>

      <select
        class="me-3"
        name="category"
        id="category"
        v-model="store.search.category"
      >
        <option selected value="">Choose series</option>
        <option
          :value="category"
          v-for="(category, index) in categoryOpt"
          :key="index"
        >
          {{ category }}
        </option>
      </select>

      <br /><br />
      <input type="submit" value="Search" />
    </form>
  </div>
</template>

<script>
import { store } from "../store";

export default {
  name: "SearchComponent",
  data() {
    return {
      store,
      categoryOpt: ["Breaking Bad", "Better Call Saul"],
    };
  },
  methods: {
    searchCharacters() {
      this.$emit("filteredChar");
    },
  },
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
