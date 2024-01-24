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
            axios,
        };
    },

    methods: {
        //Funzione che fa la richiesta  dei dati all'API
        getDataFromApi () {

            let queryString = '';
            
            //Se la lunghezza del value della select è > 0 ovvero se ho selezionato un filtro aggiungiamo il filtro allo status
            if (this.searchArch.length > 0) {
                queryString += 'status=' + this.searchArch;
            }

            //L'URL completo deve includere la stringa contenente il mio filtro
            const fullUrl = this.store.baseUrl + queryString;

            //Eseguo la richiesta al API
            axios
                .get(this.store.baseUrl)    //Richiedo i dati dal linke baseUrl (assegnato nello store)
                .then((response) => {       //Ottengo come risposta i dati
                    console.log(response.data)
                    this.store.cards = response.data.data   //Riassegno la lista di dati come se fosse la lista delle mie carte
                });
        }
        
    },

    //Definisco i componenti che mi saranno utili nel Main
    components: {
        Archetype,
        Card
    },
}
</script>

<template>
        <div class="row row-button d-flex  justify-content-start p-2">
            <div class="col-auto">
                <select class="form-select" aria-label="Default select example" v-model="store.searchArch" @change="$emit('prendoFunzioneDalFiglio')" >
                    <option selected>Open this select menu</option>
                    <!-- Richiamo la componente archetype che mi da la singola option ed eseguo un ciclo per generare iesime option ognuna con rispettivo archetype -->
                    <Archetype v-for="(arc, i) in store.archetypes" :key="i" :archetype="arc"/> <!-- In vue usare variabili per i cicli diversi (le chiavi possono coincidere) -->
                </select>
            </div>  
        </div>
    <main class="container p-5">
        <header class="row bg-dark text-light fw-bold  p-3 mb-3 rounded-4 ">
            Found {{store.cards.length}} Cards <!-- Ogni volta che applico un filtro, questo numero mostrerà le carte trovate DISPONIBILI A PAGINA (se ho detto di mostrarne max 20 e ne troverà 50, saranno comunque 20) -->
        </header>
        <div>
            <div class="row cards-container h-100 row-cols-lg-6 row-cols-md-4 row-cols-sm-3   ">
                <Card v-for="(elem, i) in store.cards" :key="i" :card="elem"/> <!-- Ciclo dentro la lista cards con elem e gli assegno il nome 'card' (ovvero l'oggetto carta con i rispettivi dati al suo interno) -->
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
    border-radius: 20px;

    .cards-container {
        display: flex;
        justify-content: center;
    }
}
</style>
