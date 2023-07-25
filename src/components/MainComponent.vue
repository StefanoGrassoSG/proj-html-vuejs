<script >
import specialtiesMainComponent from './specialtiesMainComponent.vue';
import BossMainComponent from './BossMainComponent.vue';
import EventsMainComponent from './EventsMainComponent.vue';
import CreativeMainComponent from './CreativeMainComponent.vue';
import NewsMainComponent from './NewsMainComponent.vue';
import TestimonialsMainComponent from './TestimonialsMainComponent.vue';
import VideoMainComponent from './VideoMainComponent.vue';

export default {
  components: {
    specialtiesMainComponent,
    BossMainComponent,
    EventsMainComponent,
    CreativeMainComponent,
    NewsMainComponent,
    TestimonialsMainComponent,
    VideoMainComponent
  },
  data() {
    return {

    }
  }
}
</script>

<template>
    <main>
        <specialtiesMainComponent />

        <BossMainComponent />

        <EventsMainComponent />

        <CreativeMainComponent />

        <NewsMainComponent />

        <TestimonialsMainComponent />

        <VideoMainComponent />
    </main>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables.scss" as *;

main {
  background-color: $third-bg;
}
</style>