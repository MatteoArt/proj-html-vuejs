<script>

export default {
    data() {
        return {
            cars: [
                {
                    img: "cabrio.jpg",
                    name: "Cabrio",
                    desc: "3 Listings"
                },
                {
                    img: "coupe.jpg",
                    name: "Coupe",
                    desc: "0 Listings"
                },
                {
                    img: "hatchback.jpg",
                    name: "Hatchback",
                    desc: "2 Listings"
                },
                {
                    img: "pickup.jpg",
                    name: "Pick Up",
                    desc: "0 Listings"
                },
                {
                    img: "sedan.jpg",
                    name: "Sedan",
                    desc: "3 Listings"
                },
                {
                    img: "suv.jpg",
                    name: "SUV",
                    desc: "4 Listings"
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
    <div class="car-container">
        <div class="item" v-for="car in cars">
            <div class="img-container">
                <img :src="getImgPath(car.img)" :alt="car.name">
            </div>
            <div class="desc">
                <div> {{ car.name }} </div>
                <span> {{ car.desc }} </span>
            </div>
        </div>

    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/_variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;

.car-container {
    @include d-flex;

    .item {
        flex-basis: calc(100% / 6);
        border: 1px solid whitesmoke;
        box-shadow: 6px 10px 10px -5px whitesmoke;
    }

    .img-container {

        img {
            width: 100%;
        }
    }
    .desc {
        text-align: center;
        padding: 15px;

        span {
            font-size: 14px;
            color: $color_gray;
        }
        div {
            margin-bottom: 5px;
        }
    }
}
</style>