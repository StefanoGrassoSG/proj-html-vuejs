<script >
import HeaderTopComponent from './HeaderTopComponent.vue';
import HeeaderBottomComponent from './HeeaderBottomComponent.vue';

export default {
    components: {
        HeaderTopComponent,
        HeeaderBottomComponent
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

        <HeeaderBottomComponent />
    </header>
</template>

<style lang="scss" scoped>
    header {
        background-image: url('../assets/img/rev-slider-main-home-img-03.jpg');
        background-size: cover;
        background-position: 0% 35%;
        background-repeat: no-repeat;
    }
</style>
