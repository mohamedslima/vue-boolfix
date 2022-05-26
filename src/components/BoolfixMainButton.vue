<template>
  <div class="search_and_button">
          <input 
          @keyup.enter="$emit('clickedSearch', searchText)"
          v-model="searchText"
          placeholder="Inserisci un film o una serie TV"
          type="text" 
          id="search_text">
          <button
          @click="$emit('clickedSearch', searchText)">Cerca</button>
      </div>
</template>

<script>
export default {
    name: "BoolfixMainButton",
    data: function () {
        return {
            searchText: "",
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../style/variables.scss";

    div.search_and_button {
        background-color: black;
        text-align: right;
        padding: 0 1rem 1rem;
        input {
            width: 12rem;
            height: 2rem;
            border: 1px solid $general-boolfix-border-color;
        }
        button {
            width: 5rem;
            height: 2rem;
            background-color: $general-boolfix-red-color;
            border: 2px solid $general-boolfix-border-color;
            cursor: pointer;
        }
    }
</style>