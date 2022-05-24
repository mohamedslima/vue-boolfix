<template>
  <main>
    <BoolfixMainButton @clickedSearch="searchMovie($event)" />
    <div class="boolfix_layout">
        <BoolfixFilmCard v-for="(item, index) in movieList" :key="index" :feature="item"/>
    </div>
  </main>
</template>

<script>
import BoolfixFilmCard from "./BoolfixFilmCard.vue";
import BoolfixMainButton from "./BoolfixMainButton.vue"
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
        }
    },
    methods: {
            searchMovie(searchedFilm) {
                axios
                .get("https://api.themoviedb.org/3/search/movie", {
                params: {
                    api_key: "b7b84da696134b3b85d999dbf952ff89",
                    lang: "en-US",
                    query: searchedFilm,
            },
            })
            .then((resp) => {
                this.movieList = resp.data.results;
            });
        },
    },
}
</script>

<style lang="scss" scoped>
    div.boolfix_layout {
        display: flex;
        justify-content: space-evenly;
        flex-wrap: wrap;
        width: 90%;
        margin: 0 auto;
    }
</style>