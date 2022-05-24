<template>
  <header>
      <div class="header_logo_container">BOOLFLIX</div>
  </header>
</template>

<script>
export default {
    name: "BoolfixHeader",
    data: function () {
        return {
            searchText: "",
        };
    },
}
</script>

<style lang="scss" scoped>
    header {
        background-color: black;
        div.header_logo_container {
            font-size: 2rem;
            padding: 1rem 1rem;
            color: red;
        }
    }
</style>