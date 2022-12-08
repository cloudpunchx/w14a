<template>
    <div>
        <!-- display H1 with variable we grabbed from JokeButton component via $emit -->
        <h2>{{snakeJoke}}</h2>
    </div>
</template>

<script>
    export default {
        name: "SnakeJoke",
        data() {
            return {
                snakeJoke: ""
            }
        },
        methods: {
            getSnakeJoke(snakeJoke) {
                this.snakeJoke = snakeJoke;
            }
        },
        mounted () {
            this.$root.$on(`displaySnakeJoke`, this.getSnakeJoke);
        },
    }
</script>

<style scoped>

</style>