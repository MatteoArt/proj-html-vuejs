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
        <div class="item" v-for="car in cars"
        >
        <img :src="getImgPath(car.img)" :alt="car.name">
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
    }
}
</style>