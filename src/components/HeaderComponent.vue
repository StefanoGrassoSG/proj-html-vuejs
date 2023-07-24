<script >
import HeaderTopComponent from './HeaderTopComponent.vue';

export default {
    components: {
        HeaderTopComponent
    },
    data() {
        return {

        }
    }
}
</script>

<template>
    <header>
        <HeaderTopComponent />
    </header>
</template>

<style lang="scss" scoped>
    header {
        background-image: url('../assets/img/rev-slider-main-home-img-03.jpg');
        background-size: cover;
        background-repeat: no-repeat;
        height: 600px;
    }
</style>
