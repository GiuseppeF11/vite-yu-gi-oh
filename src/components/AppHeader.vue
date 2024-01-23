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
        <div class="row border border-2">
            <div class="col-2 h-100">
                <div class="img-box h-100">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/2/21/Yu-Gi-Oh%21.png" alt="logo-YuGiOh">
                </div>
            </div>
            <div class="col h-100 d-flex justify-content-start align-items-center">
                <h1>Yu-Gi-Oh Api</h1>
            </div>
        </div>
</template>

<style lang="scss" scoped>
.row {
    max-width: 100%;
    margin: 0 auto;
    height: 10vh;
    background-color: white;
}


.col-2 {
    display: flex;
    justify-content: center;
    align-items: center;
    .img-box {
        width: 70%;
        display: flex;
        align-items: center;
        justify-content: center;

        img {
            object-fit: cover;
        }

    }

}


</style>
