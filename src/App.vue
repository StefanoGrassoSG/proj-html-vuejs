<script >
import HeaderComponent from './components/HeaderComponent.vue';

export default {
  components: {
    HeaderComponent
  },
  data() {
    return {

    }
  }
}
</script>

<template>

  <HeaderComponent />

  <main>
    MAIN
  </main>

  <footer>
    FOOTER
  </footer>
</template>

<style lang="scss">
@use "assets/scss/main";
</style>
