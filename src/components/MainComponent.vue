<script >
import SectionOneMain from './SectionOneMain.vue';
import SectionTwoMain from './SectionTwoMain.vue';
import EventsMainComponent from './EventsMainComponent.vue';
import CreativeMainComponent from './CreativeMainComponent.vue';
import NewsMainComponent from './NewsMainComponent.vue';
import TestimonialsMainComponent from './TestimonialsMainComponent.vue';

export default {
  components: {
    SectionOneMain,
    SectionTwoMain,
    EventsMainComponent,
    CreativeMainComponent,
    NewsMainComponent,
    TestimonialsMainComponent
  },
  data() {
    return {

    }
  }
}
</script>

<template>
    <main>
        <SectionOneMain />

        <SectionTwoMain />

        <EventsMainComponent />

        <CreativeMainComponent />

        <NewsMainComponent />

        <TestimonialsMainComponent />
    </main>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables.scss" as *;

main {
  background-color: $third-bg;
}
</style>