<template>
  <div id="app">
    <BoolfixHeader />
    <BoolfixMain />
  </div>
</template>

<script>
import BoolfixHeader from "./components/BoolfixHeader.vue";
import BoolfixMain from "./components/BoolfixMain.vue";

export default {
  name: 'App',
  components: {
    BoolfixHeader,
    BoolfixMain,
  },
}
</script>

<style lang="scss">
@import "./style/common.scss";
@import '~@fortawesome/fontawesome-free/css/all.min.css';

</style>
