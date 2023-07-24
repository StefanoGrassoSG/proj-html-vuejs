<script >
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';

export default {
  components: {
    HeaderComponent,
    MainComponent
  },
  data() {
    return {

    }
  }
}
</script>

<template>

  <HeaderComponent />

  <MainComponent />

  <footer>
    FOOTER
  </footer>
</template>

<style lang="scss">
@use "assets/scss/main";
</style>
