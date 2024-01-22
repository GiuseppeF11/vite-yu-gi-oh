<script>
export default {
    data() {
        return {

        };
    },
    methods: {

    }
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
            Found 39 Cards
        </header>
        <div>
            <div class="row cards-container h-100 row-cols-6 ">
                <div class="col card">
                    <div class="img-box">
                        <img src="https://www.cardtrader.com/uploads/blueprints/image/81905/show_blue-eyes-white-dragon-legendary-decks-ii-81905.png" alt="">
                    </div>
                    <div class="p-2">
                        <h5 class="name-monster text-center text-light">Alien Brain</h5>
                        <h6 class="type-monster text-center">Alien</h6>
                    </div>
                </div>
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

        .col {
            margin: 0 10px 15px;
        }
        .card {
            padding: 0;
            background-color: #D48F38;
        }
    }
}
</style>
