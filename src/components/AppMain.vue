<script>
import {store} from '../store'
import Cards from './Cards.vue'

export default {
    data() {
        return {
            store
        };
    },

    methods: {

    },

    components: {
        Cards
    },
}
</script>

<template>
        <div class="row row-button d-flex  justify-content-start p-2">
            <div class="col-auto ">
                <div class="dropdown">
                    <button class="btn border border-2 dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">
                        Alien
                    </button>
                    <ul class="dropdown-menu">
                        <li><a class="dropdown-item" href="#">Uman</a></li>
                        <li><a class="dropdown-item" href="#">Warrior</a></li>
                        <li><a class="dropdown-item" href="#">Beast</a></li>
                    </ul>
                </div>
            </div>
        </div>
    <main class="container p-5">
        <header class="row bg-dark text-light fw-bold  p-3">
            Found {{store.cards.length}} Cards
        </header>
        <div>
            <div class="row cards-container h-100 row-cols-6 ">
                <Cards v-for="(elem, i) in store.cards" :key="i" :card="elem"/>
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
