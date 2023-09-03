<script>

export default {
    data() {
        return {
            users: [
                {
                    caption: "We are a gallery vehicle dealer. Before we met this site, our sales were sluggish.",
                    img: "man1.png",
                    name: "Adam"
                },
                {
                    caption: "One of the quality websites I apply to rent a car. There are hundreds of different tools.",
                    img: "testimonial2-1.png",
                    name: "Cristian"
                },
                {
                    caption: "I was trying to sell my car. And I put it here and sold it for more than it was worth.",
                    img: "man2.png",
                    name: "Robert"
                },
                {
                    caption: "A fast and reliable vehicle selling site. Rare quality website with hundreds of model vehicles.",
                    img: "testimonial4-1.png",
                    name: "Elizabeth"
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
    <div class="user-container">
        <div class="user-card" v-for="user in users">
            <p> {{ user.caption }} </p>
            <i class="fa-solid fa-quote-right fa-2xl"></i>
            <div class="img-container">
                <img :src="getImgPath(user.img)" alt="user image">
            </div>
            <div style="margin: 30px 0;"> {{ user.name }} </div>
        </div>
    </div>
    <div class="bar">
        <span></span>
        <span></span>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/_variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;

.user-container {
    @include d-flex;
    gap: 20px;
    margin-top: 30px;
}
.user-card {
    flex-basis: calc(100% / 4);
    background-color: $color_smoke;
    padding: 20px;
    font-size: 14px;
    text-align: center;
    border-radius: 10px;

    p {
        margin-bottom: 25px;
        line-height: 1.5;
    }
    i {
        position: relative;
        font-size: 74px;
        transform: rotate(10deg) translate(-10px, -40px);
        top: 5px;
        opacity: 0.1;
        color: #4D3FA3;
    }
}
.img-container {
    width: 40%;
    margin: auto;

    img {
        width: 100%;
    }
}
.bar {
    text-align: center;
    margin-top: 15px;

    span {
        display: inline-block;
        height: 8px;
        border-radius: 8px;
        cursor: pointer;

        &:first-child {
            width: 100px;
            background-color: $color_secondary;
            margin-right: 8px;
        }

        &:last-child {
            width: 45px;
            background-color: $color_smoke;
            opacity: 0.6;
        }
    }
}
</style>