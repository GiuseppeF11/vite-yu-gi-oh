<script>
export default {
    data() {
        return {

        };
    },
    methods: {
        
    },

    props: {
        archetype: Object
    }
}
</script>

<template>
    <option 
        :value="archetype.archetype_name" >
            {{ archetype.archetype_name}}
    </option>
</template>

<style lang="scss" scoped>
</style>
