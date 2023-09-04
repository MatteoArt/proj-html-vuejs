<script>

export default {
    props: {
        navList: {
            type: Array,
            required: true
        },
        cards: {
            type: Array,
            required: true
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
    <header>
        <div class="logo-container">
            <img src="../assets/logo-autocar.png" alt="logo">
        </div>
        <nav class="nav-bar">
            <div v-for="link in navList">
                <a href="#"> {{ link }} </a>
            </div>
        </nav>
        <div class="card-container">
            <div class="card" v-for="card in cards" 
            :class="{ 'card-black' : card.caption, 'card-white' : !card.caption}">
                <div class="icon">
                    <img :src="getImgPath(card.icon)" :alt="card.icon">
                </div>
                <div v-if="card.caption" class="caption"> {{ card.caption }} </div>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
@use "../styles/partials/_variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;


header {
    @include d-flex;
    align-items: center;
    justify-content: center;
    gap: 20px;
    padding-bottom: 10px;
    background-color: $color_smoke;
    position: fixed;
    top: 0;
    z-index: 100000;
    width: 100%;
}

.card-container {
    @include d-flex;
    gap: 5px;

    .card {
        @include d-flex;
        align-items: center;
        padding: 7px 3px;
        font-size: 14px;
        font-weight: 600;
        gap: 4px;
        cursor: pointer;

    }
    .card-black {
        background-color: $color_secondary;
        color: $color_primary;
        border-radius: 3px;
    }
    
    .icon {
        width: 30px;

        img {
            width: 100%;
            filter: invert(1);
        }
    }
    .card-white {
        padding-left: 15px;
        padding-right: 15px;

        img {
            filter: invert(0);
        }
    }
}

.nav-bar {
    @include d-flex;

    div {
        padding: 5px;
    }

    a {
        font-size: 14px;
        font-weight: 600;
        text-decoration: none;
        color: $color_secondary;

        &:hover {
            color: darkblue;
        }
    }
}

.logo-container {
    width: 170px;
    padding-top: 10px;


    img {
        width: 100%;
    }
}
</style>