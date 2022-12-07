<template>
    <div>
        <button @click="makeSnake">Make Snake!</button>
        <h1>{{snakeJoke.replaceAll('','_')}}</h1>
    </div>
</template>

<script>
    export default {
        name: "SnakeJoke",
        data() {
            return {
                snakeJoke: null
            }
        },
        methods: {
            makeSnake(snakeJoke) {
                this.snakeJoke = snakeJoke;
            }
        },
        mounted () {
            this.$root.$on(`displayJoke`, this.makeSnake);
        },
    }
</script>

<style lang="scss" scoped>

</style>