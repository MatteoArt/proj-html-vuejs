<script>

export default {
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
        <div class="search-list">
            <div v-for="(item, index) in search">
                {{ item }}
            </div>
        </div>

    </section>

</template>

<style lang="scss" scoped>
@use "../styles/partials/_variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;

.search-list {
    @include d-flex;
}
</style>