<script>

import TheFooter from './TheFooter.vue';

export default {
    components: {
        TheFooter, //portalo nell'html template di questo file
    },
    data() {
        return {
           footerData: {
               accountMenu: ["My account",
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


</template>

<style>

</style>