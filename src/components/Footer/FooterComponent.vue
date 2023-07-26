<script >
import FooterTopComonent from './FooterTopComonent.vue';
import FooterBottomComponent from './FooterBottomComponent.vue';

export default {
  components: {
    FooterTopComonent,
    FooterBottomComponent
  },
  data() {
    return {

    }
  }
}
</script>

<template>
    <footer>
        <FooterTopComonent />

        <FooterBottomComponent />
    </footer>
</template>

<style lang="scss">
@use "../../assets/scss/main";
</style>
