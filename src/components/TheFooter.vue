<script>

export default {
    props: {
        menuList: {
            type: Array,
            required: true
        },
        links: {
            type: Array,
            required: true
        }
    }
}

</script>

<template>

    <footer>
        <div class="container-foot">
            <div class="foot-item"></div>
            <div class="foot-item"></div>
            <div class="foot-item">
                <ul class="list">
                    <li v-for="menu in menuList">
                        {{ menu }}
                    </li>
                </ul>
                <ul class="list">
                    <li v-for="link in links">
                        {{ link }}
                    </li>
                </ul>
            </div>
        </div>
    </footer>

</template>

<style lang="scss" scoped>
@use "../styles/partials/mixins.scss" as *;

footer {

    .container-foot {
        @include d-flex;


        .foot-item {


            &:last-child {
                @include d-flex;

            }
        }
    }
}
</style>