<template>
  <header>
      <div class="header_logo_container">BoolFix</div>
      <div class="search_and_button_header">
          <input type="text" name="" id="">
          <button>Cerca</button>
      </div>
  </header>
</template>

<script>
export default {
    name: "BoolfixHeader",
}
</script>

<style lang="scss" scoped>
    header {
        background-color: black;
        color: white;
        display: flex;
        justify-content: space-around;
        align-items: center;
        div.header_logo_container {
            font-size: 2rem;
            color: red;
        }
    }
</style>