<template>
  <header>
    <img src="../assets/momoflix.png" alt="" />
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
};
</script>

<style lang="scss" scoped>
header {
  background-color: black;
  height: 90px;
  div.header_logo_container {
    font-size: 2rem;
    padding: 1rem 1rem;
    color: red;
  }
}
</style>