<template>
    <div>
        <button @click="makeLoud">Make LOUD!</button>
        <h1>{{loudJoke.toUpperCase()}}</h1>
    </div>
</template>

<script>
    export default {
        name: "LoudJoke",
        data() {
            return {
                loudJoke: null
            }
        },
        methods: {
            makeLoud(loudJoke) {
                this.loudJoke = loudJoke;
            }
        },
        mounted () {
            this.$root.$on(`displayJoke`, this.makeLoud);
        },
    }
</script>

<style scoped>
div{
    margin: 20px;
}
</style>