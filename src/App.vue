<template>
  <header>
    <TitleComponent />
  </header>

  <section>
    <SearchComponent @filteredChar="getCharacters" />
  </section>

  <main>
    <MainContent />
  </main>
</template>

<script>
import axios from "axios";
import MainContent from "./components/MainContent.vue";
import SearchComponent from "./components/SearchComponent.vue";
import TitleComponent from "./components/TitleComponent.vue";
import { store } from "./store";

export default {
  components: {
    TitleComponent,
    SearchComponent,
    MainContent,
  },
  data() {
    return {
      // apiURL: "https://www.breakingbadapi.com/api/characters",
      // characterList: [],
      store,
      endPoint: "characters",
    };
  },
  methods: {
    getCharacters() {
      let options = null;
      if (store.search.category) {
        options = {
          params: {
            category: store.search.category,
          },
        };
      }
      // axios.get(this.apiURL).then((res) => {
      //   this.characterList = [...res.data];
      //   console.log(this.characterList);
      // });
      const charApiURL = store.apiURL + this.endPoint;
      axios.get(charApiURL, options).then((res) => {
        store.characterList = [...res.data];
      });
    },
  },
  created() {
    this.getCharacters();
  },
};
</script>

<style lang="scss" scoped></style>
