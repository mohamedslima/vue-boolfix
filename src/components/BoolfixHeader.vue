<template>
  <div class="header_container">
      <div class="header_logo_container">BoolFix</div>
      <div class="search_and_button_header">
          <input type="text" name="" id="">
          <button>Cerca</button>
      </div>
  </div>
</template>

<script>
export default {
    name: "BoolfixHeader"
}
</script>

<style lang="scss" scoped>
    div.header_container {
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