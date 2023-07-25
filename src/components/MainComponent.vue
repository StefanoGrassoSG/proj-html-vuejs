<script >
import SectionOneMain from './SectionOneMain.vue';
import SectionTwoMain from './SectionTwoMain.vue';
import EventsMainComponent from './EventsMainComponent.vue';
import CreativeMainComponent from './CreativeMainComponent.vue';
import NewsMainComponent from './NewsMainComponent.vue';

export default {
  components: {
    SectionOneMain,
    SectionTwoMain,
    EventsMainComponent,
    CreativeMainComponent,
    NewsMainComponent
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
    </main>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables.scss" as *;

main {
  background-color: $third-bg;
}
</style>