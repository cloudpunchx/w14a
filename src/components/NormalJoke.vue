<template>
    <div>
        <!-- display H1 with variable we grabbed from JokeButton component via $emit -->
        <h2>{{normalJoke}}</h2>
    </div>
</template>

<script>
    export default {
        name: "NormalJoke",
        data() {
            return {
                normalJoke: ""
            }
        },
        methods: {
            displayNormalJoke(joke) {
                this.normalJoke = joke;
            },
        },
        mounted () {
            this.$root.$on(`displayNormalJoke`, this.displayNormalJoke);
        },
    }
</script>

<style scoped>

</style>