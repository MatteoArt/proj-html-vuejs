<script>

import TheHeader from './components/TheHeader.vue';
import TheMain from './components/TheMain.vue';
import TheFooter from './components/TheFooter.vue';

export default {
    components: {
        TheHeader,
        TheMain,
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
            mainData: {
                searchList: ["Keywords","Location","All Categories",
            "Brand","Fuel Type","Transmission","Status","Search"],
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

    <TheMain :search="mainData.searchList"></TheMain>

    <TheFooter :menuList="footerData.accountMenu" 
    :links="footerData.linksMenu"></TheFooter>
</template>

<style lang="scss"></style>