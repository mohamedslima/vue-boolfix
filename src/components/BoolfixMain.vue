<template>
  <main>
    <BoolfixMainButton @clickedSearch="searchMovie($event)" />
    <div class="main_container">
      <h2>FILM</h2>
      <div class="boolfix_layout">
        <BoolfixFilmCard
          v-for="(item, index) in movieList"
          :key="index"
          :feature="item"
        />
      </div>
      <h2>Serie TV</h2>
      <div class="boolfix_layout">
        <BoolfixFilmCard
          v-for="(item, index) in seriesList"
          :key="index"
          :feature="item"
        />
      </div>
    </div>
  </main>
</template>

<script>
import BoolfixFilmCard from "./BoolfixFilmCard.vue";
import BoolfixMainButton from "./BoolfixMainButton.vue";
import axios from "axios";

export default {
  name: "BoolfixMain",
  components: {
    BoolfixFilmCard,
    BoolfixMainButton,
  },
  data() {
    return {
      movieList: [],
      seriesList: [],
      castList: [],
    };
  },
  methods: {
    searchMovie(searchFilmAndSeries) {
      const params = {
        api_key: "b7b84da696134b3b85d999dbf952ff89",
        language: "it-IT",
        query: searchFilmAndSeries,
      };

      axios
        .get("https://api.themoviedb.org/3/search/movie", { params })
        .then((resp) => {
          this.movieList = resp.data.results;
        });

      axios
        .get("https://api.themoviedb.org/3/search/tv", { params })
        .then((resp) => {
          this.seriesList = resp.data.results;
        });

        axios
        .get(`https://api.themoviedb.org/3/movie/${feature.id}/credits`, { params })
        .then((resp) => {
          this.castList = resp.data.results;
        });
    },
  },
};
</script>

<style lang="scss" scoped>
main {
  div.main_container {
    background-color: #434343;
    height: 100%;
    h2 {
      color: white;
      text-align: center;
      padding: 3rem 0;
    }
    div.boolfix_layout {
      display: flex;
      justify-content: space-evenly;
      flex-wrap: wrap;
      width: 90%;
      margin: 0 auto;
    }
  }
}
</style>