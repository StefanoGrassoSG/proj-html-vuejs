<script >
export default {
  data() {
    return {
        active: 0,
        mapdata: {
            dotImg: 'h1-contact-rev-02.png',
            img: 'h1-contact-rev-01.png',
            place: [
            'New York Coaching',
            'stockholm Coaching',
            'sidney Coaching'
            ]
        },
        clients: [
            'h4-clients-img-01.png',
            'h4-clients-img-03.png',
            'h4-clients-img-05.png',
            'h4-clients-img-07.png',
            'h4-clients-img-09.png'
        ]
    }
  },
  methods:{
    getImagePath: function(imgpath) {
            return new URL(imgpath, import.meta.url).href;
        },
    changeNewYork() {
        this.active = 0
    },
    changestockholm() {
        this.active = 1
        console.log(this.active)
    },
    changesidney() {
        this.active = 2
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
            <div class="map">
                <div class="map-img">
                    <img class="dot" @click="changeNewYork()" :src="getImagePath(`../../assets/img/${mapdata.dotImg}`)" alt="">
                    <img class="dot" @click="changestockholm()" :src="getImagePath(`../../assets/img/${mapdata.dotImg}`)" alt="">
                    <img class="dot" @click="changesidney()" :src="getImagePath(`../../assets/img/${mapdata.dotImg}`)" alt="">
                    <img :src="getImagePath(`../../assets/img/${mapdata.img}`)" alt="">
                </div>
                <div class="tag new-york" v-if="active == 0">
                    <h4>
                        {{ mapdata.place[0] }}
                    </h4>
                    <div class="more">
                        READ MORE
                    </div>
                </div>
                <div class="tag stockholm" v-if="active == 1">
                    <h4>
                        {{ mapdata.place[1] }}
                    </h4>
                    <div class="more">
                        READ MORE
                    </div>
                </div>
                <div class="tag sidney" v-if="active == 2">
                    <h4>
                        {{ mapdata.place[2] }}
                    </h4>
                    <div class="more">
                        READ MORE
                    </div>
                </div>
            </div>  
            <div class="contact">
                <h2>
                    Contact Us<span class="dot">.</span>
                </h2>
                <p>
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                </p>
                <div class="line"></div>
                <form>
                    <div class="input-wrapper">
                        <div class="name">
                            <input class="input" type="text" id="name" placeholder="Name" />
                            <label class="label" for="name">
                                Your Name
                            </label>
                        </div>

                        <div class="email">
                            <input class="input" type="text" id="email" placeholder="email" />
                            <label class="label" for="email">
                                Your Email
                            </label>
                        </div>
                    </div>
                    <div class="text-area">
                        <input class="input" type="text" id="area" placeholder="area" />
                        <label class="label" for="area">
                            Write a message...
                        </label>
                    </div>
                    <a @click.prevent href="#">SEND <span class="arrow">&#8594;</span></a>
                </form>
            </div>
        </div>

        <div class="sponsors">
            <div v-for="(singleClient, i) in clients" :key="i">
                <img :src="getImagePath(`../../assets/img/${singleClient}`)" alt="">
            </div>  
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use "../../assets/scss/partials/variables.scss" as *;
@use "../../assets/scss/partials/layout.scss" as *;

section {
    position: relative;

    .up {
        position: absolute;
        bottom: 20%;
        right: 30px;
    }
}
.container {
    display: flex;
    max-width: 1300px;
    margin: auto;
    padding-top: 150px;

    .map {
        width: 50%;
        position: relative;

        .tag {
            background-color: white;
            box-shadow: 0 0 5px rgba(0, 0, 0, 0.3);
            position: absolute;
            padding: 16px 24px;
            padding-right: 30px;
            padding-bottom: 24px;

            &.new-york {
                top: 38%;
                left: 20%;
            }
            &.stockholm {
                top: 0;
                left: 45%;
                transform: translate(-0%, -20%);
            }

            &.sidney {
                bottom: 40%;
                right: 20%;
            }

            h4 {
                font-size: 21px;
            }

            .more {
                font-weight: bold;
                cursor: pointer;
                transition: all 0.3s ease-in-out;
                display: block;

                &:hover {
                    color: $fill-color-one;
                    transform: scale(1.1);
                }
            }
        }

        .map-img {
            width: 100%;
            .dot {
                position: absolute;
                transition: all 0.1s ease-in-out;
                cursor: pointer;

                &:hover {
                    transform: scale(1.2);
                }
            }

            .dot:nth-of-type(1) {
                left: 22%;
                top: 30%;
            }

            .dot:nth-of-type(2) {
                left: 47%;
                top: 20%;
            }

            .dot:nth-of-type(3) {
                bottom: 32%;
                right: 22%;
            }
        }
    }

    .contact {
        width: 50%;
        position: relative;
        bottom: 50px;

        h2 {
            font-size: 40px;

            .dot {
                color: $fill-color-one;
            }
        }

        p {
            font-size: 22px;
            margin: 10px 0 20px 0;
        }

        .line {
            height: 2px;
            width: 10%;
            background-color: $secondary-bg;
        }

        form {
            margin-top: 30px;

            .input-wrapper {
                position: relative;
                margin-top: 30px; 
                margin-inline: auto;
                display: flex;
            }

           

            a {
            margin-right: 30px;
            text-decoration: none;
            cursor: pointer;
            padding: 16px 0px;
            padding-left: 30px;
            font-size: 14px;
            color: $third-text-color;
            background-color: $secondary-bg;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
            transition: all 0.2s ease-in-out;

            &:hover {
                box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
                background-color: $third-text-color;
                color: $secondary-bg;
            }

            

            .arrow {
                padding: 6px 14px;
                border-left: 1px solid;
                margin: 10px 0;
                margin-left: 20px;
            }
            }

            .input {
                font-size: 20px;
                width: 100%;
                padding: 8px 0;
                padding-right: 30px;
                color: $secondary-text-color;
                border: none;
                border-bottom: 1px solid #ddd;
                transition: border-color 250ms;
                background-color: transparent;

                &:focus {
                outline: none;
                border-bottom-color: #777;
                }

                &::placeholder {
                color: transparent;
                }
            }

            .name,
            .email {
                width: calc(50% - 30px);
            }
            .name {
                margin-right: 30px;
                .label {
                position: absolute;
                top: 8px;
                left: 0;
                color: $secondary-text-color;
                pointer-events: none;
                transform-origin: left center;
                transition: transform 250ms;
                font-family: "Iowan Old Style", "Palatino Linotype", "URW Palladio L", P052,
                    serif;
                }
            }

            .email {
                position: relative;
                .label {
                position: absolute;
                top: 8px;
                left: 0;
                color: $secondary-text-color;
                pointer-events: none;
                transform-origin: left center;
                transition: transform 250ms;
                font-family: "Iowan Old Style", "Palatino Linotype", "URW Palladio L", P052,
                    serif;
                }
            }

            .text-area {
                width: calc(100% - 30px);
                margin-top: 30px;
                margin-bottom: 50px;
                position: relative;
                .label {
                position: absolute;
                top: 8px;
                left: 0;
                color: $secondary-text-color;
                pointer-events: none;
                transform-origin: left center;
                transition: transform 250ms;
                font-family: "Iowan Old Style", "Palatino Linotype", "URW Palladio L", P052,
                    serif;
                }

                input {
                    padding-top: 60px;
                }
            }
            

            .input:focus + .label,
            .input:not(:placeholder-shown) + .label {
                transform: translateY(-100%) scale(0.75);
            }
        }
    }
}
.sponsors {
        max-width: 1300px;
        display: flex;
        margin: auto;
        justify-content: space-between;
        margin-top: 70px;
        padding-bottom: 70px;

        div {
            cursor: pointer;
            transition: transform 0.2s ease-in-out;
        }

        div:hover {
            filter: invert(70%) sepia(94%) saturate(6846%) hue-rotate(353deg) brightness(104%) contrast(101%);
            transform: scale(1.3);
        }
    }
</style>