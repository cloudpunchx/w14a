<template>
    <div>
        <!-- display H1 with variable we grabbed from JokeButton component via $emit -->
        <h2>{{loudJoke}}</h2>
    </div>
</template>

<script>
    export default {
        name: "LoudJoke",
        data() {
            return {
                loudJoke: ""
            }
        },
        methods: {
            makeLoud(loudJoke) {
                this.loudJoke = loudJoke;
            }
        },
        mounted () {
            this.$root.$on(`displayLoudJoke`, this.makeLoud);
        },
    }
</script>

<style scoped>
div{
    margin: 20px;
}
</style>