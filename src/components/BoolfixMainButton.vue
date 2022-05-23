<template>
  <div class="search_and_button">
          <input 
          @keyup.enter="$emit('clickedSearch', searchText)"
          v-model="searchText"
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

<style>

</style>