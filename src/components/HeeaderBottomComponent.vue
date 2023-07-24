<script >
export default {
    data() {
        return {
            slides: {
                title: 'Our Team',
                text: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Earum similique accusantium minima nesciunt, minus laborum.'
            }
        }
    }
}
</script>

<template>
    <div class="header-bottom">
        <div class="container">
            <div class="arrow-slide">
                &#8592;
            </div>
            <div class="arrow-slide">
                &#8594;
            </div>
            <div class="slide">
                <h1>
                    {{ slides.title }}<span>.</span>
                </h1>
                <p>
                    {{ slides.text }}
                </p>
                <a href="#">READ MORE <span class="arrow">&#8594;</span></a>
                <a href="#">PURCHASE <span class="arrow">&#8594;</span></a>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/layout.scss";
@use "../assets/scss/partials/variables.scss" as *;


.container {
    margin-top: 220px;
    padding-bottom: 200px;
    position: relative;

    .arrow-slide {
        position: absolute;
        font-size: 50px;
        cursor: pointer;
    }

    .arrow-slide:nth-of-type(2) {
        right: 0;
        transform: translate(-50%);
    }
    .slide {
        width: 45%;
        text-align: left;
        padding: 0 70px;
        position: relative;
        left: 200px;

        h1 {
            font-size: 100px;

            span {
                color: $fill-color-one;
            }
        }

        p {
            font-size: 19px;
            color: $secondary-text-color;
            line-height: 30px;
            margin: 25px 0px 50px 0px;
        }

        a {
            margin-right: 30px;
            text-decoration: none;
            cursor: pointer;
            padding: 16px 0px;
            padding-left: 30px;
            font-size: 14px;
            color: $primary-text-color;
            font-weight: bold;
            background-color: $primary-bg;

            .arrow {
                padding: 6px 14px;
                border-left: 1px solid;
                margin: 10px 0;
                margin-left: 20px;
            }
        }

        a:nth-of-type(2) {
            color: $third-text-color;
            background-color: $secondary-bg;
            border-left: 1px solid $third-text-color;
        }
    }

    
}
</style>