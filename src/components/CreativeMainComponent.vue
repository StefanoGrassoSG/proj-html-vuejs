<script >
export default {
  data() {
    return {

    }
  }
}
</script>

<template>
    <section>
        <div class="container">
            <div class="text">

            </div>
            <div class="lines">

            </div>
        </div>
    </section>  
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables.scss" as *;

section {
    background-color: $primary-bg;

    .container {
        max-width: 1300px;
        margin: auto;
        padding: 200px 0;
        height: 800px;
        display: flex;

        .text {
            width: 50%;
            background-color: red;
            height: 100%
        }

        .lines {
            width: 50%;
            background-color: aqua;
            height: 100%;
        }
    }
}
</style>