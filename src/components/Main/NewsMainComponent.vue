<script >
export default {
  data() {
    return {
        news: {
            title: 'Latest News',
            text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.',
            cards: [
                {
                    img: 'h1-blog-img-01.jpg',
                    date: 'May 5,2019',
                    autor: 'Amanda Doe',
                    title: 'Next Investment',
                    tag: 'Business, Leading',
                    text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam, maiores seus dolor...'
                },
                {
                    img: 'h1-blog-img-02.jpg',
                    date: 'May 5,2019',
                    autor: 'Amanda Doe',
                    title: 'Team Building',
                    tag: 'Business, Leading',
                    text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam, maiores seus dolor...'
                },
                {
                    img: 'h1-blog-img-03.jpg',
                    date: 'May 5,2019',
                    autor: 'Amanda Doe',
                    title: 'New Business Day',
                    tag: 'Business, Leading',
                    text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam, maiores seus dolor...'
                }
            ]
        }
    }
  },
  methods:{
    getImagePath: function(imgpath) {
            return new URL(imgpath, import.meta.url).href;
        }
  }
}
</script>

<template>
    <section>
        <a href="#" class="up">
            &#129057;
        </a>
        <div class="arrow-slide">
            &#8592;
        </div>
        <div class="arrow-slide">
            &#8594;
        </div>
        <div class="title">
            <img class="bg" src="../../assets/svg/svg-4.svg" alt="">
            <h2>
                {{ news.title }}<span>.</span>
            </h2>
            <p>
                {{ news.text }}
            </p>
            <div class="line">
            </div>
        </div>
        <div class="container">
            <div class="card" v-for="(singleCard, i) in news.cards" :key="i">
                <div class="img">
                    <div class="post">
                        <i class="fa-solid fa-tag fa-xs"></i>
                        {{ singleCard.tag }}
                    </div>
                    <img :src="getImagePath(`../../assets/img/${singleCard.img}`)" alt="">
                </div>
                <div class="info">
                    <i class="fa-regular fa-clock fa-xs"></i> {{ singleCard.date }}
                    <i class="fa-regular fa-user fa-xs"></i> {{ singleCard.autor }}
                </div>
                <h3>
                    {{ singleCard.title }}
                </h3>
                <p>
                    {{ singleCard.text }}
                </p>
                <div class="more">
                    READ MORE
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
        top: 40%;
        right: 30px;
        transform: translate(-0%, -50%);
    }
    .arrow-slide {
        font-size: 40px;
        position: absolute;
        top: 60%;
        cursor: pointer;
    }

    .arrow-slide:nth-of-type(1) {
        left: 100px;
    }

    .arrow-slide:nth-of-type(2) {
        right: 100px;
    }
}
.title {
    text-align: center;
    padding-top: 90px;

    .bg {
        position: absolute;
        left: 100px;
        top: 0;
        transform: translate(-0%, -20%);
        z-index: 1;
    }

    h2 {
        font-size: 35px;

        span {
            color: $fill-color-one;
        }
    }

    p {
        margin: 10px 0 20px 0;
        color: $secondary-text-color;
    }

    .line {
        height: 2px;
        width: 3%;
        background-color: $fill-color-one;
        margin: auto;
        margin-bottom: 70px;
    }
}

.container {
    max-width: 1300px;
    display: flex;
    margin: auto;
    padding-bottom: 120px;

    .card {
        width: calc(100% / 3);
        margin: 0 15px;
        z-index: 999;

        .info {
            color: $secondary-text-color;

            i {
                color: $fill-color-one;
                filter: opacity(0.5);
            }
        }

        .img {
            position: relative;

            .post {
                background-color: $fill-color-one;
                position: absolute;
                bottom: 15px;
                right: 15px;
                color: $third-text-color;
                padding: 10px 20px;
            }

            img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            margin-bottom: 20px;
        }
        }

        h3 {
            margin-top: 5px;
            margin-bottom: 10px;
            font-size: 22px;
        }

        p {
            margin-bottom: 13px;
            color: $secondary-text-color;
        }

        .more {
            cursor: pointer;
            font-weight: bold;
        }
    }
}
</style>
