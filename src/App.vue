<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import LoadingPage from './components/LoadingPage.vue';
import Card from './components/Card.vue'
import Archetype from './components/Archetype.vue';
import {store} from './store.js'
import axios from 'axios';

export default {
    data() {
        return {
            store,
            axios
        };
    },
    components: {
        AppHeader,
        AppMain,
        LoadingPage,
        Archetype,
        Card,
    },  

    methods: {

        getApi () {

            //Parte la richiesta senza filtro
            if (this.store.searchArch == '')
            axios
            .get(this.store.baseUrl)
            .then((response) => {
                console.log(response.data)
                this.store.cards = response.data.data
            });
            
            //Parte la richiesta con il filtro archetype
            else {
                axios
                .get(this.store.baseUrl, {
                    params: {
                        archetype: this.store.searchArch,
                    }
                })
                .then((response) => {
                    console.log(response.data)
                    this.store.cards = response.data.data
                });
            
            }
        }
        
    },

    created() {
        this.getApi()
            
        axios
            .get(this.store.arcUrl)
            .then((response) => {
                this.store.archetypes = response.data         
                console.log(this.store.archetypes[1].archetype_name)      
            });
    }
}
</script>

<template>
    <body>
        <AppHeader />
        <AppMain @ciao="getApi" />
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
