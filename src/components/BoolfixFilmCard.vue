<template>
  <div class="boolfix_card_layout">
    <div class="image_container">
      <img
        v-if="feature.poster_path !== null"
        :src="`https://www.themoviedb.org/t/p/w342${feature.poster_path}`"
        alt=""
      />
    </div>
    <div>{{ feature.title }} {{ feature.name }}</div>
    <div>{{ feature.original_title }} {{ feature.original_name }}</div>
    <div>
      <FlagIcons :langCode="feature.original_language" />
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
  width: 300px;
  margin-top: 1rem;
  background-color: rgba(0, 0, 0, 0.039);
  text-align: center;
  div.image_container {
    img {
      width: 240px;
    }
  }
}
</style>