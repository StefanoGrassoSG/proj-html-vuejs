<script >
export default {
  data() {
    return {
        data: {
            title: 'Creative Leader',
            text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorem expedita accusamus iste sunt sapiente molestias? At, nam molestiae? Laudantium alias iure totam explicabo, voluptatum aperiam quam atque libero ex repudiandae?Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima, labore.',
            list: [
                {
                    name: 'Mentorship',
                    width: '78%'
                },
                {
                    name: 'Education',
                    width: '95%'
                },
                {
                    name: 'Learning',
                    width: '65%'
                },
                {
                    name: 'Motivation',
                    width: '83%'
                }
            ]
        }
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
        <a href="#" class="up" @click.prevent="scrollToTop">
            &#129057;
        </a>
        <div class="container">
            <div class="text">
                <h2>
                    {{ data.title }}<span>.</span>
                </h2>
                <div class="line">

                </div>
                <p>
                    {{ data.text }}
                </p>
                <div class="more">
                    READ MORE
                </div>
            </div>

            <div class="lines">
                <div class="element" v-for="(singleElement, i) in data.list" :key="i">
                    <div class="data-container">
                        <h3>
                            {{ singleElement.name }}
                        </h3>
                        <span>
                            {{ singleElement.width }}
                        </span>
                    </div>
                    <div class="line-data">
                        <div class="line-progress" :style="{ width: singleElement.width}">

                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>  
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables.scss" as *;
@use "../assets/scss/partials/layout.scss";

section {
    background-color: $primary-bg;
    position: relative;

    a {
        position: absolute;
        top: 40%;
        right: 30px;
        transform: translate(-0%, -50%);
    }
    .container {
        max-width: 1300px;
        margin: auto;
        padding: 120px 0;
        display: flex;

        .text {
            width: 50%;
            height: 100%;
            padding-right: 70px;

            h2 {
            font-size: 35px;
            margin-bottom: 20px;
            line-height: 25px;

            span {
                color: $fill-color-one;
            }
        }

        .line {
            height: 2px;
            background-color: $fill-color-one;
            width: 10%;
            margin-bottom: 20px;
        }

        p {
            line-height: 25px;
            color: $secondary-text-color;
            margin-bottom: 15px;
        }

        .more {
            font-weight: bold;
            cursor: pointer;
        }
    }

       
        

        .lines {
            width: 50%;
            height: 100%;

            .element {
                margin-bottom: 25px;
                line-height: 25px;
            }

            .data-container {
                display: flex;
                justify-content: space-between;

                h3 {
                    margin-bottom: 10px;
                }
            }

            .line-data {
                height: 4px;
                background-color: lightgray;

                .line-progress {
                    height: 4px;
                    background-color: $fill-color-one;
                }
            }
        }
    }
}
</style>