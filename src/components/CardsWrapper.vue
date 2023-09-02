<script>

export default {
    data() {
        return {
            cardsList: [
                {
                    imgName: "bmw-8.jpg",
                    title: "BMW M9",
                    modello: "Cabrio",
                    caratt: [
                        "34.000",
                        "BMW",
                        "Electric"
                    ]
                },
                {
                    imgName: "bmw88.jpg",
                    title: "BMW M8",
                    modello: "Cabrio",
                    caratt: [
                        "34.000",
                        "BMW",
                        "Diesel"
                    ]
                },
                {
                    imgName: "bmw442.jpg",
                    title: "BMW 4",
                    modello: "Cabrio",
                    caratt: [
                        "34.000",
                        "BMW",
                        "Gasoline"
                    ]
                },
                {
                    imgName: "yeni.jpg",
                    title: "Seat Ibiza",
                    modello: "Hatchback",
                    caratt: [
                        "27.000",
                        "Seat",
                        "Electric"
                    ]
                },
                {
                    imgName: "suv2022.jpg",
                    title: "Seat Arona",
                    modello: "SUV",
                    caratt: [
                        "68.000",
                        "Seat",
                        "Gasoline"
                    ]
                },
                {
                    imgName: "taigo.jpg",
                    title: "Volswagen Taigo",
                    modello: "SUV",
                    caratt: [
                        "52.000",
                        "Volswagen",
                        "Electric"
                    ]
                },
                {
                    imgName: "vw-t-cross.jpg",
                    title: "Volswagen T-Cross",
                    modello: "SUV",
                    caratt: [
                        "47.000",
                        "Volswagen",
                        "Diesel"
                    ]
                },
                {
                    imgName: "volkswagen.jpg",
                    title: "Volswagen Passat",
                    modello: "Sedan",
                    caratt: [
                        "32.000",
                        "Volswagen",
                        "Diesel"
                    ]
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
    <div class="cards">
        <div class="card" v-for="card in cardsList">
            <div class="img-container">
                <img :src="getImgPath(card.imgName)" :alt="card.modello">
            </div>
            <div class="info">
                <div> {{ card.title }} <i class="fa-solid fa-circle-check"></i></div>
                <div class="model"> {{ card.modello }} </div>
                <div class="flex-info">
                    <div>
                        <span><i class="fa-solid fa-dollar-sign"></i> {{ card.caratt[0] }}</span>
                        <span class="span-block"><i class="fa-solid fa-car"></i> {{ card.caratt[1] }}</span>
                        <span><i class="fa-solid fa-gas-pump"></i> {{ card.caratt[2] }}</span>
                    </div>
                    <div class="heart">
                        <i class="fa-solid fa-heart"></i>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/_variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;

.cards {
    @include d-flex;
    flex-wrap: wrap;
    margin: 35px 0 8px;
    row-gap: 15px;

    .card {
        flex-basis: calc(100% / 4);
        padding: 8px;
        font-size: 14px;
        border: 1px solid whitesmoke;
        box-shadow: 6px 10px 10px -5px whitesmoke;
    }

    .img-container {

        img {
            width: 100%;
        }
    }

    .flex-info {
        @include d-flex;
        justify-content: space-between;
    }

    .span-block {
        display: inline-block;
        margin: 0 7px;
    }
    .model {
        padding: 7px 0;
    }

    .info {
        padding: 7px 3px;
    }
    .heart {
        color: $color_gray;
    }
}
</style>