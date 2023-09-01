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

</style>