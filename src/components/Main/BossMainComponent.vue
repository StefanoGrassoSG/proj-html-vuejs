<script >


export default {
  data() {
    return {
      currentSlide: 0,
      slides: [
        'h1-img-01.jpg',
        'h1-img-02.jpg',
        'h1-img-03.jpg'
      ],
      boss: {
        name: 'Jason Bickford',
        role: 'Founder and Executive Director',
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Deserunt aspernatur ratione odit officia cupiditati...'
      }
    }
  },
  methods: {
    getImagePath: function(imgpath) {
            return new URL(imgpath, import.meta.url).href;
        },
    scrollToTop() {
      window.scrollTo({ top: 0, behavior: "smooth" });
    },
    slideNext() {
        if(this.currentSlide == this.slides.length - 1) {
            this.currentSlide = 0
        }
        else {
            this.currentSlide++
        }
    },
    slidePrev() {
        if(this.currentSlide == 0) {
            this.currentSlide = this.slides.length -1
        }
        else {
            this.currentSlide--
        }
    }
  }
}
</script>

<template>
    <section>
      <a href="#" class="up" @click.prevent="scrollToTop">
          &#129057;
      </a>
      <img class="bg" src="../../assets/svg/svg-4.svg" alt="">
      <div class="container">
        <div
          class="slide"
          v-for="(singleSlide, i) in slides"
          :key="i"
          v-show="i === currentSlide"
        >
          <div class="arrow-container">
            <span class="arrow-back" @click="slidePrev()">&#8592;</span>
            <span class="arrow-next" @click="slideNext()">&#8594;</span>
          </div>
          <img :src="getImagePath(`../../assets/img/${slides[i]}`)" alt="">
      </div>
          <div class="founder">
            <h2>
              {{ boss.name }}
            </h2>
            <small>
              {{ boss.role }}
            </small>
            <div class="line"></div>
            <p>
              {{ boss.text }}
            </p>
            <div class="bottom-content">
              <div class="icons">
                <div>
                  <i class="fa-brands fa-linkedin fa-xl"></i>
                </div>
                <div>
                  <i class="fa-brands fa-square-facebook fa-xl"></i>
                </div>
                <div>
                  <i class="fa-brands fa-square-twitter fa-xl"></i>
                </div>
              </div>
              <div class="firma">
                <img src="../../assets/img/firma.png" alt="">
              </div>
            </div>
          </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use "../../assets/scss/partials/variables.scss" as *;
@use "../../assets/scss/partials/layout.scss";

section {
  position: relative;

  a  {
      position: absolute;
      right: 30px;
      bottom: 60px;
    }
  .bg {
      position: absolute;
      right: 80px;
      top: 0;
      z-index: 1;
    }

}
.container {
  max-width: 1300px;
  margin: auto;
  display: flex;
  padding-left: 20px;
  padding-top: 80px;
  padding-bottom: 100px;

  .slide {
    width: 45%;
    position: relative;

    img {
      width: 120%;
      display: block;
    }

    .arrow-container {
      position: absolute;
      bottom: 0;
      left: 0;
      padding: 18px;
      background-color: $secondary-bg;
      user-select: none;

      > span {
        cursor: pointer;
        color: $third-text-color;
        display: inline-block;
        transition: all 0.3s ease-in-out;
      }

      > span:hover {
        transform: scale(1.5);
      }
      .arrow-back {
        margin-right: 10px;
      }
    }
  }
  .founder {
    background-color: $primary-bg;
    height: 100%;
    padding: 70px 50px;
    padding-right: 100px;
    width: 55%;
    z-index: 999;
    position: relative;
    top: 70px;

    .bottom-content {
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 70%;
    }

    .icons {
      display: flex;

      div {
        margin-right: 10px;
        color: $fill-color-one;
        cursor: pointer;
        transition: all 0.3s ease-in-out;

        &:hover {
          color: black;
        }
      }
    }

    h2 {
      font-size: 35px;
    }

    small,
    p {
      color: $secondary-text-color;
    }

    p {
      font-size: 17px;
      line-height: 30px;
    }

    .line {
      height: 2px;
      width: 10%;
      background-color: $secondary-bg;
      margin: 16px 0;
    }
  }
}
</style>