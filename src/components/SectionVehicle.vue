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
            <div class="img-container-autocar">
                <img src="../assets/about-car.png" alt="autocar">
                <div class="circle circle-left">
                    <h2>24</h2>
                    <span>Years of<br> Experience</span>
                </div>
                <div class="circle circle-right">
                    <h2>240</h2>
                    <span>Special Expert<br> Team</span>
                </div>
            </div>
        </div>
        <div class="item">
            <h2>Want to buy or sell a vehicle?</h2>
            <p>
                You can put your vehicles for sale by registering on our website. Whether you are a dealer or sell
                personally. Sell ​​your vehicle in the most profitable way. With this system, which has millions of members,
                you will be able to buy and sell vehicles quickly.
            </p>
            <img src="../assets/divider.jpg" alt="divider">
            <div class="info-vehicle">
                <div class="icon-img-container">
                    <img src="../assets/car.webp" alt="car">
                </div>
                <div class="cap">
                    <div>Model Vehicles</div>
                    <p>
                        We are sure that you will find vehicles of suitable models on our website.
                    </p>
                </div>
            </div>
            <div class="info-vehicle" style="margin-top: 27px;">
                <div class="icon-img-container">
                    <img src="../assets/car-repair.png" alt="car repair">
                </div>
                <div class="cap">
                    <div>2nd Hand Vehicles</div>
                    <p>
                        You can put your used vehicles for sale by adding them to our website.
                    </p>
                </div>
            </div>
            <span class="btn"><span class="align">Get to know us <i class="fa-solid fa-arrow-right fa-sm"></i></span></span>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/_variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;

@mixin my-btn {
    display: inline-block;
    padding: 15px 25px;
    color: $color_primary;
    background-color: $color_secondary;
    font-size: 14px;
    font-weight: 600;
    cursor: pointer;
}

.wrapper {
    @include d-flex;

    .item {

        h2 {
            padding-bottom: 8px;
        }

        p {
            font-size: 14px;
            margin-bottom: 12px;
            line-height: 1.5;
        }


        &:first-child {
            flex-basis: 60%;
            background-image: url("../assets/background-car.png");
            background-size: contain;
            background-repeat: no-repeat;
            background-position: center;
        }

        &:last-child {
            flex-basis: 40%;
            padding: 30px;
        }
    }
}

.info-vehicle {
    @include d-flex;
    gap: 10px;
    margin-top: 12px;
}

.cap {

    div {
        font-weight: 600;
        margin-bottom: 10px;
    }

    p {
        font-size: 14px;
    }
}

.icon-img-container {
    width: 50px;
    padding-top: 5px;

    img {
        width: 100%;
    }
}

.btn {
    @include my-btn;
    margin-top: 4px;
}

.align {
    @include align-button;
    gap: 5px;

    i {
        margin-top: 2px;
    }
}

.img-container-autocar {
    width: 500px;
    margin: auto;
    position: relative;

    img {
        width: 100%;
    }
}

.circle {
    width: 162px;
    height: 162px;
    background-color: $color_secondary;
    border-radius: 50%;
    position: absolute;
    color: $color_primary;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;

    span {
        font-size: 14px;
        font-weight: 600;
    }
}

.circle-left {
    top: 0;
    left: 0;
}

.circle-right {
    bottom: 0;
    right: 0;
}</style>