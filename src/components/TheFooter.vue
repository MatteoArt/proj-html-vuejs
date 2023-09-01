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
            <div class="foot-item">
                <div class="logo">
                    <img src="../assets/logo-footer-autocar.png" alt="logo footer">
                </div>
                <ul class="info">
                    <li>
                       <div class="icon"> <img src="../assets/locator.png" alt="locator"> </div>
                       <span>New Jersey, USA</span>
                    </li>
                    <li>
                        <i class="fa-solid fa-phone-volume fa-lg"></i>
                        <span>+ 1 (234) 567 89 10</span>
                    </li>
                    <li>
                        <i class="fa-regular fa-envelope fa-lg"></i>
                        <span>example@example.com</span>
                    </li>
                </ul>
                <div class="socials">
                    <i class="fa-brands fa-facebook-f"></i>
                    <i class="fa-brands fa-instagram" style="margin: 0 20px;"></i>
                    <i class="fa-brands fa-twitter"></i>
                </div>
            </div>
            <div class="foot-item pd-top-footer">
                <div class="foot-title">Join Our Newsletter</div>
                <p class="caption">Subscribe to be informed about our services and products.</p>
                <input type="text" placeholder="Your Email Address">
                <div id="subscribe">Subscribe <i class="fa-solid fa-arrow-right fa-sm"></i></div>
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
        <p id="copyright">© 2022 Autocar - All Rights Reserved.</p>
    </footer>

</template>

<style lang="scss" scoped>
@use "../styles/partials/_variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;

footer {
    background-color: $color_secondary;
    color: $color_primary;
    padding-bottom: 20px;
    .container-foot {
        @include d-flex;
        justify-content: center;
        gap: 65px;
        padding: 35px 0;


        .foot-item {

            p {
                margin: 10px 0 25px;
            }


            &:last-child {
                @include d-flex;

            }
        }

        input {
            padding: 10px;
            border: 1px solid $color_gray;
            border-radius: 5px;
            width: 100%;
            color: $color_gray;
        }
    }
}
ul.info {
    list-style-type: none;
    margin-top: 15px;

    .icon {
        width: 18px;
    }
    img {
        width: 100%;
    }
    li {
        @include d-flex;
        font-size: 14px;
        align-items: center;
        gap: 5px;
        padding: 5px 0;
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
.logo {
    width: 150px;
    

    img {
        width: 100%;
    }
}
#copyright {
    font-size: small;
    text-align: center;
}
.socials {
    text-align: center;
    margin-top: 10px;
}
#subscribe {
    background-color: $color_primary;
    color: $color_gray;
    font-size: small;
    text-align: center;
    border-radius: 5px;
    padding: 12px 0;
    margin-top: 2px;
    cursor: pointer;
}
</style>