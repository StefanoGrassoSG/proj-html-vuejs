<script >
export default {
  data() {
    return {
        footerData: {
            about : {
                title: 'About',
                text: 'We created Everlead to effectively become the stepping stone towards meeting all your goals & achieving business success.'
            },
            twitter: {
                title: 'Twitter',
                textOne: '@alisasadadm Hi @alisasadadm, can you please submit a ticket at https://t.co/JLV61aXG7d and one of our support agent...https://t.co/yk57k1S9bS',
                textTwo: '@HenrySefaBoaky1 Check out our theme Gioia which has all necessary elements to build a multi vendor marketplace. https://t.co/c9BIYxZBIL'
            },
            links: {
                title: 'Important Links',
                link: [
                    'About me',
                    'About us',
                    'Language packs',
                    'Become a Coach',
                    'Monthly events'
                ]
            },
            contact: {
                title: 'Contact me',
                address: '457 BigBlue Street,NY 10013',
                number: '315|5512-2579',
                mail: 'everlead@mikado.com'
            }
        }
    }
  }
}
</script>

<template>
    <div class="footer-top">
        <div class="container">
            <div class="card about">
                <h3>
                    {{ footerData.about.title }}
                </h3>
                <div class="line"></div>
                <p>
                    {{ footerData.about.text }}
                </p>
                <div class="socials">
                    <a href="">
                        <i class="fa-brands fa-linkedin fa-2xl"></i>
                    </a>
                    <a href="">
                        <i class="fa-brands fa-square-facebook fa-2xl"></i>
                    </a>
                    <a href="">
                        <i class="fa-brands fa-square-twitter fa-2xl"></i>
                    </a>
                </div>
            </div>
            <div class="card twitter">
                <h3>
                    {{ footerData.twitter.title }}
                </h3>
                <div class="line"></div>
                <ul class="fa-ul">
                    <li>
                        <span class="fa-li"><i class="fa-brands fa-twitter fa-xl"></i></span>
                        <a href="#">@alisasadadm</a> Hi <a href="#">@alisasadadm</a>, can you please submit a ticket at <a href="#">https://t.co/JLV61aXG7d</a> and one of our support agent...<a href="#">https://t.co/yk57k1S9bS</a>
                    </li>
                    <li>
                        <span class="fa-li"><i class="fa-brands fa-twitter fa-xl"></i></span>
                        <a href="#">@HenrySefaBoaky1</a> Check out our theme Gioia which has all necessary elements to build a multi vendor marketplace. <a href="#">https://t.co/c9BIYxZBIL</a>
                    </li>
                </ul>
            </div>
            <div class="card links">
                <h3>
                    {{ footerData.links.title }}
                </h3>
                <div class="line"></div>
                <ul>
                    <li v-for="(singleLink, i) in footerData.links.link"> 
                        <a href="">
                            {{ singleLink }}
                        </a>
                    </li>
                </ul>
            </div>
            <div class="card contact">
                <h3>
                    {{ footerData.contact.title }}
                </h3>
                <div class="line"></div>
                <ul>
                    <li>
                        <i class="fa-solid fa-location-dot"></i>
                        {{ footerData.contact.address }}
                    </li>
                    <li>
                        <i class="fa-solid fa-phone"></i>
                        {{ footerData.contact.number }}
                    </li>
                    <li>
                        <i class="fa-regular fa-envelope"></i>
                        {{ footerData.contact.mail }}
                    </li>
                </ul>

                <div class="input-wrapper">
                    <input type="text" id="name" placeholder="Your Name">
                    <label for="name">SUBSCRIBE</label>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
@use "../../assets/scss/main";
@use "../../assets/scss/partials/variables.scss" as *;

.footer-top {
    background-color: $lightBlack-bg;
    padding: 100px 0;

    .container {
        max-width: 1300px;
        margin: auto;
        display: flex;

        .twitter {
            ul {
                margin: 25px;

                i {
                    color: $fill-color-one;
                }

                li {
                    padding-left: 10px;
                    margin-bottom: 20px;
                }
            }
        }

        .links {
            ul {
                list-style: none;
                li {

                    a {

                        text-decoration: none;
                    }

                    a:hover {
                        color: $fill-color-one;
                        text-decoration: underline $fill-color-one;
                    }
                }
            }
        }

        .contact {
            li {
                list-style: none;
                i {
                    color: $fill-color-one;
                    margin-right: 5px;
                    vertical-align: middle;
                }
            }

            .input-wrapper {
                position: relative;

                label {
                    position: absolute;
                    right: 0;
                    bottom: 0;
                    color: white;
                    cursor: pointer;
                }

                label:hover {
                    color: $fill-color-one;
                }

                input {
                margin-top: 40px;
                border: none;
                border-bottom: 1px solid white;
                background-color: transparent;
                color: $secondary-text-color;
                width: 100%;
                height: 30px;
                user-select: none;

                &:focus {
                outline: none;
                border-bottom-color: $fill-color-one;
                }
            }
            }
        }

        .card {
            width: calc(100% / 4);
            margin-right: 30px;
            line-height: 30px;

            .socials {
                display: flex;
                margin-top: 20px;

                a {
                    margin-right: 10px;
                    color: $third-text-color;
                }

                a:hover {
                    color: $fill-color-one;
                }
            }

            h3 {
                color: $third-text-color;
                font-size: 25px;
            }

            .line {
                height: 2px;
                width: 10%;
                background-color: $secondary-bg;
                margin: 20px 0;
            }

            p,
            ul,
            li {
                color: $secondary-text-color;

                a {
                    color: $secondary-text-color;
                }
            }
        }
    }
}
</style>
