<script>

export default {
    data() {
        return {
            slideList: [
                {
                    img: "slider-autocar-5.jpg",
                    title: "Buy And Sell Your Car At Its Value",
                    txt: "Find the right price and dealer."
                },
                {
                    img: "slider-autocar-6.jpg",
                    title: "The Easiest Way To Buy And Sell Vehicles",
                    txt: "Find the right price and dealer."
                }
            ],
            activeImageIndex: 0,
            classVisible: "d-block"
        }
    },
    methods: {
        getImgPath(img) {
            return new URL(`../assets/${img}`, import.meta.url).href;
        },
        showSlide(index) {
            if (index === this.activeImageIndex) {
                return this.classVisible;
            } else {
                return '';
            }
        },
        prevClick() {
            const limit = this.slideList.length - 1;

            if (this.activeImageIndex === 0) {
                this.activeImageIndex = limit;
            } else {
                this.activeImageIndex = this.activeImageIndex - 1;
            }
        },
        nextClick() {
            const limit = this.slideList.length - 1;

            if (this.activeImageIndex === limit) {
                this.activeImageIndex = 0;
            } else {
                this.activeImageIndex = this.activeImageIndex + 1;
            }
        }
    }
}

</script>

<template>
    <div class="slider">
        <div class="button-prev" @click="prevClick">
            <i class="fa-solid fa-chevron-left fa-2xl"></i>
        </div>
        <div class="button-next" @click="nextClick">
            <i class="fa-solid fa-chevron-right fa-2xl"></i>
        </div>
        <div class="slide-item d-none" v-for="(slide, i) in slideList" :class="showSlide(i)">
            <img :src="getImgPath(slide.img)" :alt="`slide-${i}`">
            <div class="desc">
                <h1> {{ slide.title }} </h1>
                <div class="txt"> {{ slide.txt }} </div>
                <div class="btn-info">
                    <span class="align">
                        Learn More <i class="fa-solid fa-arrow-right fa-sm"></i>
                    </span>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/_variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;

@mixin my-btn {
    background-color: $color_secondary;
    color: $color_primary;
    width: 60px;
    height: 60px;
    border-radius: 5px;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    z-index: 100;
}

.slider {
    position: relative;
}

.d-none {
    display: none;
}

.d-block {
    display: block;
}

.button-prev {
    @include my-btn;
    position: absolute;
    left: 50px;
    top: 48%;

    &:hover {
        background-color: rgba(56, 56, 56, 0.5);
    }
}

.button-next {
    @include my-btn;
    position: absolute;
    right: 50px;
    top: 48%;

    &:hover {
        background-color: rgba(56, 56, 56, 0.5);
    }
}

.slide-item {
    height: 550px;
    position: relative;

    img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }
}

.desc {
    position: absolute;
    left: 180px;
    top: 35%;
    color: $color_primary;
    width: 400px;

    .txt {
        margin-top: 10px;
        font-weight: 600;
        font-size: 15px;
    }

    .btn-info {
        display: inline-block;
        color: $color_primary;
        background-color: $color_secondary;
        padding: 15px 25px;
        font-size: 14px;
        font-weight: 600;
        cursor: pointer;
        margin-top: 20px;

        .align {
            @include align-button;
            gap: 4px;

            i {
                margin-top: 2px;
            }
        }
    }
}</style>