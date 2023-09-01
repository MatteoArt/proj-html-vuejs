<script>

import CarList from './CarList.vue';

export default {
    components: {
        CarList,
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
            
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use "../styles/partials/_variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;

.container {
    max-width: 1100px;
    margin: 0 auto;
}
.btn-search {
    border: 1px solid $color_gray;
    color: $color_gray;
    padding: 15px 3px 15px 20px;
    font-size: small;
    border-radius: 4px;

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
</style>