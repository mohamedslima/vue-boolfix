<template>
  <div class="boolfix_card_layout">
      <div>{{ feature.title }}</div>
      <div>{{ feature.original_title }}</div>
      <div>
          <FlagIcons :langCode="feature.original_language"/>
      </div>
      <div>{{ feature.vote_average }}</div>
  </div>
</template>

<script>
import FlagIcons from "./FlagIcons.vue"

export default {
    name: "BoolfixFilmCard",
    components: {
        FlagIcons,
    },
    props: {
        feature: Object,
    }
}
</script>

<style lang="scss" scoped>
    div.boolfix_card_layout {
        margin-top: 1rem;
        width: 280px;
        background-color: rgba(0, 0, 0, 0.039);
    }
</style>