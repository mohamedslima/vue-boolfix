<template>
  <div>
    <span class="fi" :class="`fi-${nationCode}`"></span>
  </div>
</template>

<script>
export default {
  name: "FlagIcons",
  props: {
    langCode: String,
  },
  computed: {
    nationCode: function () {
      switch (this.langCode) {
        case "it":
          return "it";
        case "fr":
          return "fr";
        case "en":
          return "us";
        case "es":
          return "es";
        case "uk":
          return "ua";
          default:
              return "unknown";
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../node_modules/flag-icons/css/flag-icons.css";
</style>