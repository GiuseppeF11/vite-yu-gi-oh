<script>
export default {
    data() {
        return {

        };
    },
    methods: {
        
    },

    props: {
        card: Object
    }
}
</script>

<template>
    <div class="col card">
        <div class="img-box">
            <img :src="card.card_images[0].image_url" :alt="card.name">
        </div>
        <div class="p-2 text-box">
            <h5 class="name-monster text-center text-light">{{card.name}}</h5>
            <h6 class="type-monster text-center">{{card.archetype}}</h6>
        </div>
    </div>
</template>

<style lang="scss" scoped>

.col {
            margin: 0 10px 15px;
        }
        .card {
            border: 5px solid #464F64;
            padding: 10px;
            background-color: #D48F38;
            box-shadow: 10px 10px 20px #464F64;

            .text-box {
                display: flex;
                flex-direction: column;
                .name-monster {
                    min-height: 100px;
                }
            }
        }
</style>
