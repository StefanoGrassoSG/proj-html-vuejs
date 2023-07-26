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
    <section>
        <div class="spin">
            <img src="../../assets/svg/svg-8.svg" alt="">
        </div>
        <div class="cart">
            <img src="../../assets/svg/svg-7.svg" alt="">
        </div>
        <a href="#" class="up" @click.prevent="scrollToTop">
            &#129057;
        </a>
        <a href="#" class="up" @click.prevent="scrollToTop">
            &#129057;
        </a>
        <i class="fa-solid fa-play fa-4x"></i>
        <div class="img">
            <img src="../../assets/img/h1-img-04.jpg" alt="">
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use "../../assets/scss/partials/variables.scss" as *;
@use "../../assets/scss/partials/layout.scss";

section {
    position: relative;

    .cart,
    .spin {
        position: absolute;
        top: 0;
        transform: translate(+0%, -50%);
        right: 0;
        width: 35px;
        height: 35px;
        cursor: pointer;

        img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
    }

    .cart {
        top: 45px;
        background-color: $primary-bg;
        padding: 10px;

        &:hover {
            background-color: rebeccapurple;
        }
    }

    .spin {
        background-color: $purple-bg;
        padding: 7px;

        &:hover {
            background-color: rebeccapurple;
        }
    }

    a {
        position: absolute;
        top: 20%;
        right: 30px;
        transform: translate(-0%, -50%);
    }

    a:nth-of-type(2) {
        top: 99%;
    }

    i {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        color: $third-text-color;
        cursor: pointer;
        transition: all 0.3s ease-in-out;

        &:hover {
            transform: translate(-50%, -50%) scale(1.5);
            color: $fill-color-one;
        }
    }
    .img > img {
        width: 100%;
    }
}
</style>