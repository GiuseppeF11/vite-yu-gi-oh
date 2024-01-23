<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import LoadingPage from './components/LoadingPage.vue';
import Card from './components/Card.vue'
import {store} from './store'
import axios from 'axios';

export default {
    data() {
        return {
            store
        };
    },
    components: {
        AppHeader,
        AppMain,
        LoadingPage,
        Card,
    },  

    methods: {
        
    },

    created() {
        axios
            .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0')
            .then((response) => {
                console.log(response.data.data[0].card_images[0].image_url)
                this.store.cards = response.data.data
            });
    }
}
</script>

<template>
    <body>
        <AppHeader />
        <AppMain />
        <!-- <LoadingPage/> -->
    </body>    
</template>

<style lang="scss">
@use "assets/scss/main" as *;
@import "assets/scss/partials/reset";

body {
    background-color: #D48F38;
}

</style>
