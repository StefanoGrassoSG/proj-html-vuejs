<script >
export default {
  components: {
  },
  data() {
    return {
        specialties: {
            title: 'Our specialties',
            text: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Praesentium, sint.',
            cards: [
                {
                    title: 'Knowing',
                    img: 'svg-0.svg',
                    text: 'Lorem ipsum dolor sit amet, quis consect.'
                },
                {
                    title: 'Selling',
                    img: 'svg-1.svg',
                    text: 'Lorem ipsum dolor sit amet, quis consect.'
                },
                {
                    title: 'Learning',
                    img: 'svg-2.svg',
                    text: 'Lorem ipsum dolor sit amet, quis consect.'
                },
                {
                    title: 'Contact',
                    img: 'svg-3.svg',
                    text: 'Lorem ipsum dolor sit amet, quis consect.'
                }
            ]
        }
    }
  },
  methods: {
    getImagePath: function(imgpath) {
            return new URL(imgpath, import.meta.url).href;
        },
    scrollToTop() {
      window.scrollTo({ top: 0, behavior: "smooth" });
    }    
  }
}
</script>

<template>
    <section>
        <a href="#" class="up" @click.prevent="scrollToTop">
            &#129057;
        </a>
        <div class="container">
            <div class="title">
                <h2>
                    {{ specialties.title }}<span>.</span>
                </h2>
                <p>
                    {{ specialties.text }}
                </p>
                <div class="line-orange">
                </div>
            </div>

            <div class="specialties">
                <div class="card" v-for="(singleCard, i) in specialties.cards">
                    <div class="img">
                        <img :src="getImagePath(`../../assets/svg/${singleCard.img}`)" alt="">
                    </div>
                    <h4>
                        {{ singleCard.title }}
                    </h4>
                    <p>
                        {{ singleCard.text }}
                    </p>
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

    a {
        position: absolute;
        right: 20px;
        bottom: 20px;
    }
    .container {
        width: 90%;
        display: block;
        margin: auto;
        background-color: white;
        position: relative;
        bottom: 40px;

        .title {
            text-align: center;
            padding-top: 60px;
            
            h2 {
                font-size: 45px;
            }

            h2 > span {
                color: $fill-color-one;
            }

            p {
                margin: 15px 0 30px 0;
                color: $secondary-text-color;
            }

            .line-orange {
                height: 2px;
                width: 3%;
                margin: auto;
                background-color: $secondary-bg;
            }
        }

        .specialties {
            display: flex;
            width: 80%;
            margin: auto;
            margin-top: 50px;
            padding-bottom: 70px;

            .card {
                width: calc(100% / 4);
                padding: 20px 30px;
                text-align: center;
                cursor: pointer;

                .img {
                    transition: all 0.3s ease-in-out;
                }

                &:hover {
                    border: 2px solid white;
                    border-radius: 10px;
                    box-shadow: 0 0 5px rgba(0, 0, 0, 0.3);
                }

                &:hover .img {
                    transform: scale(1.2);
                }

                h4 {
                    margin: 15px 0;
                    font-size: 18px;
                }
            }
        }
    }
}
</style>