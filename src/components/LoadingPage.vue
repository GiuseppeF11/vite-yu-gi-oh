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
    <div class="d-flex justify-content-center align-items-center container-loader">
        <div class="loader"></div>
    </div>
</template>

<style lang="scss" scoped>
.container-loader{
  height: 100vh;
}
.loader {
  border: 30px solid #f3f3f3;
  border-top: 30px solid #626262;
  border-radius: 50%;
  width: 200px;
  height: 200px;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
</style>
