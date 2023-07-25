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
            <div class="events-container">

            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables.scss" as *;
section {
    background-image: url('../assets/img/h1-img-09.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    padding: 200px 0;
    .container {
        max-width: 1300px;
        margin: auto;
        height: 800px;
        background-color: rebeccapurple;

        .events-container {
            width: 40%;
            
        }
    }
}
</style>