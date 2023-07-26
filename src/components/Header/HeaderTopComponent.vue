<script >
export default {
    data() {
        return {
            currentActivePage: 0,
            topData: {
                logoName: 'Everlead',
                logo: 'logo-img-01.png',
                nav: [
                    'HOMES',
                    'PAGES',
                    'BLOG',
                    'SHOP',
                    'EVENTS',
                    'ELEMENTS'
                ]
            }
        }
    },
    methods: {
        getImagePath: function(imgpath) {
            return new URL(imgpath, import.meta.url).href;
        }
    }
}
</script>

<template>  
    <div class="header-top">
        <div class="container">
            <div class="logo">
                <img :src="getImagePath(`../../assets/img/${topData.logo}`)" :alt='topData.logoName'>
            </div>

            <div class="nav-bar">
                <ul>
                    <li v-for="(singleLink, i) in topData.nav" :key="i" :class="i == currentActivePage ? 'active-link' : ''">
                        {{ singleLink }}
                    </li>
                </ul>
                <i class="fa-solid fa-magnifying-glass fa-rotate-90" style="color: #000000;"></i>
                <i class="fa-solid fa-list" style="color: #000000;"></i>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../../assets/scss/partials/layout.scss";
@use "../../assets/scss/partials/variables.scss" as *;

.container {
    display: flex;
    justify-content: space-between;
    padding: 30px 60px;
    align-items: center;
}
.logo {
    width: 10%;

    img {
        width: 100%;
        height: 100%;
        object-fit: contain;
    }
}

.nav-bar {
    display: flex;
    align-items: center;

    .active-link {
        color: $fill-color-one;
    }

    .active-link::before {
            content: "\2192";
            margin-right: 5px;
            font-size: 22px;
        }
    .fa-magnifying-glass {
        margin-right: 30px;
    }

    .fa-magnifying-glass,
    .fa-list {
        cursor: pointer;
    }
}
.nav-bar > ul {
    list-style: none;
    display: inline-block;

    li {
        display: inline-block;
        margin-right: 30px;
        font-weight: bold;
        cursor: pointer;
    }
}
</style>
