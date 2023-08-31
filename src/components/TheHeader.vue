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
            <div class="card" v-for="card in cards">
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
}

.card-container {
    @include d-flex;

    .card {
        @include d-flex;
        align-items: center;


    }
    .icon {
        width: 30px;

        img {
            width: 100%;
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