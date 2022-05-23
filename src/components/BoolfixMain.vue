<template>
  <main>
    <BoolfixFilmCard />
  </main>
</template>

<script>
import BoolfixFilmCard from "./BoolfixFilmCard.vue";
import axios from "axios";

export default {
    name: "BoolfixMain",
    components: {
        BoolfixFilmCard,
    },
    data() {
        return {
            movieList: [],
        }
    },
    methods: {
        axios
        .get("https://api.themoviedb.org/3/search/movie", {
          params: {
            api_key: "b7b84da696134b3b85d999dbf952ff89",
            lang: "en-US",
            page: 1,
            query: searchedFilm,
          },
        })
    }
}
</script>

<style>
</style>