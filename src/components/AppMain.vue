<script>
import { resolveTransitionHooks } from 'vue';
import {store} from '../store.js'
import Card from './Card.vue'
import Archetype from './Archetype.vue';
import axios from 'axios';

export default {
    data() {
        return {
            store,
            axios
        };
    },

    methods: {
        
    },

    components: {
        Archetype,
        Card
    },
}
</script>

<template>
    <form>
        <div class="row row-button d-flex  justify-content-start p-2">
            <div class="col-auto">
                <select class="form-select" aria-label="Default select example">
                    <option selected>Select Menù</option>
                    <Archetype v-for="(arc, i) in store.archetypes" :key="i" :archetype="arc"
                    />
                </select>
            </div>  
        </div>
    </form>
    <main class="container p-5">
        <header class="row bg-dark text-light fw-bold  p-3 mb-3">
            Found {{store.cards.length}} Cards
        </header>
        <div>
            <div class="row cards-container h-100 row-cols-6 ">
                <Card v-for="(elem, i) in store.cards" :key="i" :card="elem"/>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
.row-button {
    width: 85%;
    margin: 10px auto;
    
    button {
        background-color: white;
    }
}

.container {
    min-height: 50vh;
    background-color: white;

    .cards-container {
        display: flex;
        justify-content: center;
    }
}
</style>
