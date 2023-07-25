<script >
export default {
  data() {
    return {
        events: [
            {
                day: '07',
                month: 'jan',
                year: '2022',
                name: 'Melbourne Coaching',
                place: 'Cambridge, MA 02138,USA',
                starting: '9:00 am',
                end: '5:00 pm'
            },
            {
                day: '11',
                month: 'jan',
                year: '2022',
                name: 'New York Coaching',
                place: 'Cambridge, MA 02138,USA',
                starting: '9:00 am',
                end: '5:00 pm'
            },
            {
                day: '21',
                month: 'jan',
                year: '2022',
                name: 'London Coaching',
                place: 'Cambridge, MA 02138,USA',
                starting: '9:00 am',
                end: '5:00 pm'
            }
        ]
    }
  },
  methods: {
    scrollToTop() {
      window.scrollTo({ top: 0, behavior: "smooth" });
    }
  }
}
</script>

<template>
    <section>
        <a href="#" class="up" @click.prevent="scrollToTop">
            &#129057;
        </a>
        <div class="container">
            <div class="events-container">
                <div class="title">
                    <h3>
                         Upcoming Events
                    </h3>
                </div>
                <div class="event" v-for="(singleEvent, i) in events" :key="i">
                    <div class="date">
                        <div class="day">
                            {{ singleEvent.day }}
                        </div>
                        <div class="month"> 
                            {{ singleEvent.month }},{{ singleEvent.year }}
                        </div>
                    </div>
                    <div class="info">
                        <h5>
                            {{ singleEvent.name }}
                        </h5>
                        <div class="time">
                            <i class="fa-regular fa-clock fa-xs"></i>
                            <span>
                                {{ singleEvent.starting }} - {{ singleEvent.end }},{{ singleEvent.month }} {{ singleEvent.day }},{{ singleEvent.year }}
                            </span>
                        </div>
                        <div class="place">
                            <i class="fa-solid fa-location-dot fa-xs"></i>
                            <span>
                                {{ singleEvent.place }}
                            </span>
                        </div>
                        <div class="more">
                            READ MORE
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables.scss" as *;
@use "../assets/scss/partials/layout.scss";

section {
    background-image: url('../assets/img/h1-img-09.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    padding: 200px 0;
    position: relative;

    a {
        position: absolute;
        top: 50%;
        right: 30px;
        transform: translate(-0%, -50%);
    }
    .container {
        max-width: 1300px;
        margin: auto;

        .events-container {
            width: 45%;
            height: 100%;
            background-color: $third-bg;

            .event:hover {
                background-color: $hover-bg;
            }

            .event {
                border-top: 1px solid lightgrey;
                padding: 25px 35px;
                padding-bottom: 40px;
                cursor: pointer;
                transition: all 0.3s ease-in-out;

                .info {

                    h5 {
                        font-size: 25px;
                        line-height: 20px;
                    }

                    .more {
                        font-weight: bold;
                        margin-top: 20px;
                    }

                    .time,
                    .place {
                        color: $secondary-text-color;

                        i {
                            color: $fill-color-one;
                            filter: opacity(0.4);
                            margin-right: 15px;
                        }
                    }

                    .time {
                        margin-top: 10px;
                        margin-bottom: 5px;

                        i {
                            vertical-align: middle;
                        }
                    }
                }
               .date {
                background-color: $secondary-bg;
                height: 100%;
                text-align: center;
                color: $third-text-color;
                padding: 10px;
                padding-top: 0;
                margin-right: 20px;

                .day {
                    font-weight: bold;
                    font-size: 20px;
                }

                .month {
                    font-size: small;
                }
            }
            }

            .title {
                font-size: 32px;              
                padding: 20px 35px 35px
            }

            .event {
                display: flex;
            }
        }
    }
}
</style>