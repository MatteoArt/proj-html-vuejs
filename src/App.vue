<script>

import TheHeader from './components/TheHeader.vue';
import TheFooter from './components/TheFooter.vue';

export default {
    components: {
        TheHeader,
        TheFooter,
    },
    data() {
        return {
            headerData: {
                navLinks: [
                    "Home",
                    "About Us",
                    "Vehicles",
                    "Dealers",
                    "Packages",
                    "Blog",
                    "Contact"
                ],
                headerCard: [
                    {
                        icon: "padlock.png",
                        caption: "My Account"
                    },
                    {
                        icon: "add.png",
                        caption: "Add Car"
                    },
                    {
                        icon: "bars-staggered-solid.svg",
                        caption: ""
                    },
                    {
                        icon: "headphones.png",
                        caption: "+1 (234) 567 89 10"
                    }
                ]
            },
            footerData: {
                accountMenu: ["My Account",
                    "My Account",
                    "Checkout",
                    "Cart",
                    "Packages",
                    "Add Car"
                ],
                linksMenu: ["Quick Links",
                    "Home",
                    "About Us",
                    "Blog",
                    "Contact",
                    "Refund & Returns"
                ]
            },
        }

    }
}

</script>

<template>
    <TheHeader :navList="headerData.navLinks" 
    :cards="headerData.headerCard"></TheHeader>

    <TheFooter :menuList="footerData.accountMenu" 
    :links="footerData.linksMenu"></TheFooter>
</template>

<style lang="scss"></style>