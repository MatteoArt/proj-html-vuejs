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
            <div class="foot-item pd-top-footer">
                <div class="foot-title">Join Our Newsletter</div>
                <p class="caption">Subscribe to be informed about our services and products.</p>
                <input type="text" placeholder="Your Email Address">
            </div>
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
@use "../styles/partials/_variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;

footer {

    .container-foot {
        @include d-flex;


        .foot-item {


            &:last-child {
                @include d-flex;

            }
        }

        input {
            padding: 10px;
            border: 1px solid $color_gray;
            border-radius: 5px;
            width: 100%;
        }
    }
}

ul.list {
    list-style-type: none;
    padding: 0 15px;

    li {
        padding: 3px;

        &::before {
            content: "-";
            font-weight: bold;
            padding-right: 5px;
        }

        &:first-child {
            margin-bottom: 10px;
            font-weight: 600;
            font-size: large;

            &::before {
                content: '';
                padding: 0;
            }
        }
    }
}
.foot-title {
    font-size: large;
    font-weight: 600;
}
.caption {
    font-size: small;
}
.pd-top-footer {
    padding-top: 3px;
}
</style>