<script >
export default {
  data() {
    return {

    }
  },
  methods: {
    scrollToTop() {
      window.scrollTo({ top: 0, behavior: "smooth" });
    }
  }
}
</script>

<template>
    <div class="footer-bottom">
        <a href="#" class="up" @click.prevent="scrollToTop">
            &#129057;
        </a>
        <span>
            Copyright Everlead© MikadoThemes
        </span>
    </div>
</template>

<style lang="scss">
@use "../../assets/scss/main";
@use "../../assets/scss/partials/variables.scss" as *;
@use "../../assets/scss/partials/layout.scss";

.footer-bottom {
    text-align: center;
    color: $third-text-color;
    background-color: $secondary-bg;
    padding: 10px 0;
    position: relative;

    a {
        position: absolute;
        top: 0;
        right: 20px;
        transform: translate(-0%, -50%);
    }
}
</style>
