<template>
  <div class="boolfix_card_layout">
    <img
      v-if="feature.poster_path !== null"
      :src="`https://www.themoviedb.org/t/p/w342${feature.poster_path}`"
      alt=""
    />
    <img v-else src="../assets/No_image_available.svg.png" alt="" />
    <div class="text_container">
      <div class="film_title">
        TITOLO: {{ feature.title }} {{ feature.name }}
      </div>
      <div class="film_original_title">
        TITOLO ORIGINALE: {{ feature.original_title }}
        {{ feature.original_name }}
      </div>
      <div class="nation_production">
        Paese di produzione: <FlagIcons :langCode="feature.original_language" />
      </div>
      <div>
        voto:
        <span>
          <i
            v-for="(item, index) in 5"
            :key="index"
            class="fa-star"
            :class="index <= filledStars() ? 'fas' : 'far'"
          ></i>
        </span>
      </div>
    </div>
  </div>
</template>

<script>
import FlagIcons from "./FlagIcons.vue";

export default {
  name: "BoolfixFilmCard",
  components: {
    FlagIcons,
  },
  props: {
    feature: Object,
  },
  methods: {
    filledStars() {
      return Math.ceil(this.feature.vote_average / 2);
    },
  },
};
</script>

<style lang="scss" scoped>
div.boolfix_card_layout {
  width: 22%;
  margin-top: 1.5rem;
  text-align: center;
  border: 1px solid lightgray;
  color: white;
  position: relative;
  img {
    height: 100%;
    width: 100%;
  }
}
div.boolfix_card_layout:hover div.text_container {
  display: block;
}
div.text_container {
  position: absolute;
  top: 0;
  left: 0;
  background-color: rgba(0, 0, 0, 0.658);
  height: 100%;
  width: 100%;
  display: none;
  padding-top: 2.5rem;
  div.film_title {
    font-size: 1.5rem;
  }
  div.film_original_title {
    font-size: 1rem;
    padding: 1rem 0;
  }
  div.nation_production {
    padding: 1rem 0;
  }
}
div {
  span {
    i.fa-star {
      color: gold;
    }
  }
}
</style>