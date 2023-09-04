<script>

import CarList from './CarList.vue';
import CardsWrapper from './CardsWrapper.vue';
import UserList from "./UserList.vue";
import ArticleList from './ArticleList.vue';
import SectionVehicle from './SectionVehicle.vue';

export default {
    components: {
        CarList,
        CardsWrapper,
        UserList,
        ArticleList,
        SectionVehicle
    },
    props: {
        search: {
            type: Array,
            required: true
        }
    }
}

</script>

<template>
    <section>
        <div class="container">
            <div class="search-list">
                <div class="btn-search" v-for="(item, index) in search"
                :class="{ 'pd-search' : index < 2  || index > 6} ">
                    {{ item }}
                    <span
                    v-if="index>=2 && index<=6"><i class="fa-solid fa-caret-down fa-sm"></i></span>
                </div>
            </div>
            
            <CarList></CarList>
            <CardsWrapper></CardsWrapper>
            <div class="row-btn">
            <span class="btn">
                <span class="align-btn">Show All Cars <i class="fa-solid fa-arrow-right fa-sm"></i></span>
            </span></div>

        </div>
        <div class="container" style="padding: 60px 0;">
            <SectionVehicle></SectionVehicle>
        </div>
    </section>
    <section id="about">
        <div class="container">
            <div class="about">
                <i class="fa-regular fa-thumbs-up fa-2xl"></i>
                <span style="display: block;">
                    <i class="fa-regular fa-star"></i>
                    <i class="fa-regular fa-star"></i>
                    <i class="fa-regular fa-star"></i>
                </span>
                <h2 style="margin: 30px 0 15px;">What Are Our Customers Saying ?</h2>
                <p style="font-size: 14px;">Opinions from our happy customers.</p>
            </div>
            <UserList></UserList>
        </div>
    </section>
    <section style="background-color: #FBFBFB; padding: 20px 0 50px;">
        <div class="container">
            <div class="last-section-div">
                <div class="logo-section-container">
                    <img src="../assets/LogoSection.png" alt="logo">
                </div>
                <h2>Resent Articles</h2>
                <p style="font-size: 14px;">Useful information about car.</p>
            </div>
            <ArticleList></ArticleList>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use "../styles/partials/_variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;

section {
    padding: 30px 0;
}
section#about {
    min-height: 500px;
    background-image: url("../assets/comment-bg-autocar.jpg");
    background-size: cover;
}
.container {
    max-width: 1200px;
    margin: 0 auto;
}
.row-btn {
    text-align: center;
}
.btn {
    display: inline-block;
    padding: 15px 25px;
    color: $color_primary;
    background-color: $color_secondary;
    font-size: 14px;
    font-weight: 600;
    cursor: pointer;
}
.about {
    text-align: center;
    color: $color_primary;

}
.align-btn {
    @include d-flex;
    align-items: center;

    i {
        padding-left: 4px;
    }
}
.btn-search {
    border: 1px solid $color_gray;
    color: $color_gray;
    padding: 15px 3px 15px 20px;
    font-size: small;
    border-radius: 4px;
    cursor: pointer;

    span {
        margin-left: 15px;
    }

    &:last-child {
        border-color: $color_secondary;
        background-color: $color_secondary;
        color: $color_primary;
        font-weight: 600;
    }
}

.pd-search {
    padding: 15px 20px;
}
.search-list {
    @include d-flex;
    justify-content: center;
    gap: 10px;
    margin-bottom: 20px;
}
.last-section-div {
    text-align: center;
    color: $color_secondary;

    h2 {
        margin: 12px 0;
    }
}

.logo-section-container {
    width: 90px;
    margin: auto;

    img {
        width: 100%;
    }
}
</style>