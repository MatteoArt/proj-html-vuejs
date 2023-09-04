<script>

export default {
    data() {
        return {

        }
    }
}

</script>

<template>
    <div class="wrapper">
        <div class="item">
            <h3>Want to buy or sell a vehicle?</h3>
            <p>
                You can put your vehicles for sale by registering on our website. Whether you are a dealer or sell
                personally. Sell ​​your vehicle in the most profitable way. With this system, which has millions of members,
                you will be able to buy and sell vehicles quickly.
            </p>
        </div>
        <div class="item"></div>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/_variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;

.wrapper {
    @include d-flex;

    .item {
        flex-basis: 50%;
    }
}
</style>