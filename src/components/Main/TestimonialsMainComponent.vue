<script >
export default {
  data() {
    return {
        currentTestimonials: 0,
        testimonials:{
            title: 'TESTIMONIALS',
            people: [
                {
                    name: 'Cynthia Clark',
                    review: '"Lorem ipsum dolor sit amet consectetur adipisicing elit. Reprehenderit voluptates voluptatum ipsum debitis iusto ad a. Nemo culpa voluptatum est."',
                    photo: 'h3-img-04.png'
                },
                {
                    name: 'Samantha Blirk',
                    review: '"Lorem ipsum dolor sit amet consectetur adipisicing elit. Reprehenderit voluptates voluptatum ipsum debitis iusto ad a. Nemo culpa voluptatum est."',
                    photo: 'h3-img-07.png'
                },
                {
                    name: 'Stephanie Loson',
                    review: '"Lorem ipsum dolor sit amet consectetur adipisicing elit. Reprehenderit voluptates voluptatum ipsum debitis iusto ad a. Nemo culpa voluptatum est."',
                    photo: 'h3-img-08.png'
                }
            ]
        }
    }
  },
  methods:{
    getImagePath: function(imgpath) {
            return new URL(imgpath, import.meta.url).href;
    },
    testimonialsNext() {
        if(this.currentTestimonials == this.testimonials.people.length - 1) {
            this.currentTestimonials = 0
        }
        else {
            this.currentTestimonials++
        }
    },
    testimonialsPrev() {
        if(this.currentTestimonials == 0) {
            this.currentTestimonials = this.testimonials.people.length -1
        }
        else {
            this.currentTestimonials--
        }
    },
    scrollToTop() {
      window.scrollTo({ top: 0, behavior: "smooth" });
    }
  },
  computed: {
    changePosition() {
        if(this.currentTestimonials == 1) {
            return '33%'
        }
        else if(this.currentTestimonials == 2) {
            return '66%'
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
        <h2>
            {{ testimonials.title }}
        </h2>
        <div class="container">
            <div class="arrow-slide" @click="testimonialsPrev()">
                &#8592;
            </div>
            <div class="arrow-slide" @click="testimonialsNext()">
                &#8594;
            </div>
            <template v-for="(singlePerson, i) in testimonials.people" :key="i">
                <div class="slide" v-show="i == currentTestimonials">
                    <div class="photo">
                        <img :src="getImagePath(`../../assets/img/${singlePerson.photo}`)" alt="">
                    </div>
                    <h5>
                        {{ singlePerson.name }}
                    </h5>
                    <p>
                        {{ singlePerson.review }}
                    </p>
                    <div class="bar">
                        <div class="number">
                            01
                        </div>
                        <div class="progress-bar">
                            <div class="progress" :style="{ left: changePosition}">

                            </div>
                        </div>
                        <div class="number">
                            03
                        </div>
                    </div>
                </div>
            </template>  
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use "../../assets/scss/partials/variables.scss" as *;
@use "../../assets/scss/partials/layout.scss";

section {
    background-color: $lightBlack-bg;
    text-align: center;
    padding-top: 50px;
    padding-bottom: 120px;
    position: relative;

    a {
        position: absolute;
        top: 20%;
        right: 30px;
        transform: translate(-0%, -50%);
    }

    .container {
        position: relative;

        .arrow-slide {
            font-size: 40px;
            color: $third-text-color;
            position: absolute;
            top: 15%;
            cursor: pointer;
            user-select: none;
            transition: all 0.2s ease-in-out;
            padding: 10px;

            &:hover {
                transform: scale(1.4);
                filter: brightness(120%);
            }
        }

        .slide {
            width: 40%;
            margin: auto;

            .photo {
                width: 100px;
                height: 100px;
                margin: auto;

                img {
                border: 5px solid white;
                border-radius: 100px;
                width: 100%;
                height:100%;
                object-fit: cover;
            }
            }

            h5 {
                color: $third-text-color;
                font-size: 18px;
                margin: 20px 0;
            }

            p {
                color: $secondary-text-color;
                font-size: 20px;
            }

            .bar {
                display: flex;
                align-items: center;
                justify-content: center;
                margin-top: 20px;

                .number {
                    color: $secondary-text-color;
                }

                .progress-bar {
                    height: 1px;
                    width: 15%;
                    background-color: rgb(48, 47, 47);
                    margin: 0 10px;
                    margin-top: 6px;
                    display: flex;
                    position: relative;

                    .progress {
                        height: 1px;
                        width: calc(100% / 3);
                        background-color: $secondary-text-color;
                        transition: all 5s ease-in-out;
                        position: absolute;
                        left: 0;
                    }
                }
            }
        }
        
        .arrow-slide:nth-of-type(1) {
        left: 100px;
        
        &:hover {
            left: 90px;
        }
        }

        .arrow-slide:nth-of-type(2) {
        right: 100px;
        
        &:hover {
            right: 90px;
        }
        }
    }

    h2 {
        color: $light-black-tx;
        font-size: 200px;
        line-height: 100px;
    }
}
</style>