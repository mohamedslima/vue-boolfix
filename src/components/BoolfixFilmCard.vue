<template>
  <div class="boolfix_card_layout">
    <div class="image_container">
      <img
        v-if="feature.poster_path !== null"
        :src="`https://www.themoviedb.org/t/p/w342${feature.poster_path}`"
        alt=""
      />
    </div>
    <div class="text_container">
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
  margin-top: 1.5rem;
  text-align: center;
  border: 1px solid lightgray;
  color: white;
    div.image_container {
      width: 300px;
      height: 500px;
      img {
        height: 100%;
        width: 100%;
      }
    }
  div.text_container {
    div {
      span {
        i.fa-star {
          color: gold;
        }
      }
    }
  }
}
</style>