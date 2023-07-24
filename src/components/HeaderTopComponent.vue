<script >
export default {
    data() {
        return {
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
                <img :src="getImagePath(`../assets/img/${topData.logo}`)" :alt='topData.logoName'>
            </div>

            <div class="nav-bar">
                <ul>
                    <li v-for="(singleLink, i) in topData.nav" :key="i">
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
@use "../assets/scss/partials/layout.scss";
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
