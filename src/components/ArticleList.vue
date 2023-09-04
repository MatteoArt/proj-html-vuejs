<script>

export default {
    data() {
        return {
            articleList: [
                {
                    img: "news-autocar1.jpg",
                    title: "Why is BMW loved?",
                    description: "BMWs have a different line with their designs and almost [...]",
                },
                {
                    img: "news-autocar2.jpg",
                    title: "How solid id Audi?",
                    description: "According to Euro NCAP data with different test organizations, there [...]",
                },
                {
                    img: "news-autocar-3.jpg",
                    title: "What brand is Skoda?",
                    description: "Skoda is one of the leading automotive manufacturers on the [...]",
                },
                {
                    img: "news-autocar4.jpg",
                    title: "Is the Auris diesel?",
                    description: "You will have a quieter vehicle that burns less than [...]",
                }
            ]
        }
    },
    methods: {
        getImgPath(img) {
            return new URL(`../assets/${img}`, import.meta.url).href;
        }
    }
}

</script>

<template>

    <div class="articles">
        <div class="item" v-for="article in articleList">
            <div class="img-container">
                <img :src="getImgPath(article.img)" alt="img news auto">
            </div>
            <div class="info">
                <span>06.07.2022 - Auto Car</span>
                <h3> {{ article.title }} </h3>
                <p> {{ article.description }} </p>
                <span class="btn">More</span>
            </div>
        </div>
    </div>

</template>

<style lang="scss" scoped>
@use "../styles/partials/_variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;

$a: 100%;
$b: 20px;
.articles {
    @include d-flex;
    flex-wrap: wrap;
    margin-top: 20px;

    .item {
        flex-basis: calc((#{$a} / 4) - #{$b});
        margin: 0 10px;
        padding: 20px;
        background-color: $color_primary;
        border: 1px solid whitesmoke;
        box-shadow: 3px 3px 13px 0 rgba(0, 0, 0, 0.096);
        border-radius: 10px;

        .img-container {

            img {
                width: 100%;
            }
        }
    }
    .info {
        text-align: center;

        span {
            font-size: 14px;
            font-weight: 600;
        }

        h3 {
            margin: 12px 0;
        }

        p {
            font-size: 14px;
            margin-bottom: 18px;
        }
    }
    span.btn {
        display: inline-block;
        padding: 20px 35px;
        color: $color_primary;
        background-color: $color_secondary;
        font-size: 14px;
        font-weight: 600;
        cursor: pointer;
    }
}
</style>