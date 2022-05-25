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
      <span>{{ feature.vote_average }}</span>
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
  methods: {},
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