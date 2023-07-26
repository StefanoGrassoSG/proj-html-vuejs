<script >
export default {
  data() {
    return {
        mapdata: {
            dotImg: 'h1-contact-rev-02.png',
            img: 'h1-contact-rev-01.png',
            place: 'New York Coaching'
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
        <div class="container">
            <div class="map">
                <div class="map-img">
                    <img class="dot" :src="getImagePath(`../assets/img/${mapdata.dotImg}`)" alt="">
                    <img class="dot" :src="getImagePath(`../assets/img/${mapdata.dotImg}`)" alt="">
                    <img class="dot" :src="getImagePath(`../assets/img/${mapdata.dotImg}`)" alt="">
                    <img :src="getImagePath(`../assets/img/${mapdata.img}`)" alt="">
                </div>
                <div class="tag">
                    <h4>
                        {{ mapdata.place }}
                    </h4>
                    <dv class="more">
                        READ MORE
                    </dv>
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
    </section>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables.scss" as *;

.container {
    display: flex;
    max-width: 1300px;
    margin: auto;
    padding: 150px 0;

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
            top: 40%;
            left: 22%;
            cursor: pointer;

            h4 {
                font-size: 21px;
            }

            .more {
                font-weight: bold;
            }
        }

        .map-img {
            width: 100%;
            .dot {
                position: absolute;
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
</style>