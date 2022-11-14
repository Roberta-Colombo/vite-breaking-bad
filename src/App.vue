<template>
  <header>
    <TitleComponent />
  </header>

  <section>
    <SearchComponent />
  </section>

  <main>
    <MainContent :characters="characterList" />
  </main>
</template>

<script>
import axios from "axios";
import MainContent from "./components/MainContent.vue";
import SearchComponent from "./components/SearchComponent.vue";
import TitleComponent from "./components/TitleComponent.vue";

export default {
  components: {
    TitleComponent,
    SearchComponent,
    MainContent,
  },
  data() {
    return {
      apiURL: "https://www.breakingbadapi.com/api/characters",
      characterList: [],
    };
  },
  methods: {
    getCharacters() {
      axios.get(this.apiURL).then((res) => {
        this.characterList = [...res.data];
        console.log(this.characterList);
      });
    },
  },
  created() {
    this.getCharacters();
  },
};
</script>

<style lang="scss" scoped></style>
