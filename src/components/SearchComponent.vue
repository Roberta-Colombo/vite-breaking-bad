<template>
  <div class="my-container">
    <form
      class="mt-4 mb-2 d-flex justify-content-start align-items-center"
      @submit.prevent="searchCharacters"
      @reset="resetSearch"
    >
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
      <input class="ms-3" type="reset" value="Cancel search" />
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
    resetSearch() {
      store.search.category = "";
      this.$emit("filteredChar");
    },
  },
};
</script>

<style lang="scss" scoped>
@use "../assets/styles/partials/variables" as *;

input,
select {
  background-color: $white;
  color: black;
  padding: 5px 6px;
  border-radius: 5px;
  font-weight: 500;
}

input:hover {
  color: $lightgreen;
}

label {
  font-size: 1.3rem;
}
</style>
