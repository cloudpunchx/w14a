<template>
    <div>
        <div>
            <!-- This button will get a Joke using the 'getJoke' method which holds API -->
            <h1>Let's have some laughs!</h1>
            <h3>First get a joke, then select a display option!</h3>
            <button @click="getJoke">Get Joke!</button>
        </div>
        <!-- 3 Selection Buttons only appear IF there is a Joke -->
        <div v-if="joke">
            <!-- after click, trigger $emit to other components -->
            <button @click="makeNormal">Normal Joke!</button>
            <button @click="makeLoud">Make LOUD!</button>
            <button @click="makeSnake">Make Snake!</button>
        </div>
    </div>
</template>

<script>
import axios from 'axios';

    export default {
        name: "JokeButton",
        data() {
            return {
                joke: "",
                normalJoke: "",
                loudJoke: "",
                snakeJoke: "",
            }
        },
        methods: {
            // getJoke triggered by @click on button above
            getJoke(){
                axios.request({
                url: "https://geek-jokes.sameerkumar.website/api?format=json",
                method: "GET"
            }).then((response)=>{
                // I want THIS.joke(my key values in return-data) to become response.data.joke (taken from API call)
                this.joke = response.data.joke;
                this.normalJoke = response.data.joke;
                // I want Upper Case for loudjoke
                this.loudJoke = response.data.joke.toUpperCase();
                // I want snake case for snakejoke
                this.snakeJoke = response.data.joke.replaceAll('','_');
            }).catch((error)=>{
                console.log(error);
            });
            },
            // after click, emit to NormalJoke component
            makeNormal(){
                this.$root.$emit(`displayNormalJoke`, this.normalJoke);
            },
            // after click, emit to LoudJoke component
            makeLoud(){
                this.$root.$emit(`displayLoudJoke`, this.loudJoke);
            },
            // after click, emit to SnakeJoke component
            makeSnake(){
                this.$root.$emit(`displaySnakeJoke`, this.snakeJoke);
            },
        },
    }
</script>

<style scoped>
h1{
    color: #E86252;
}
h3{
    color: #E86252;
}
button{
    cursor: pointer;
    color: hotpink;
    font-size: 18pt;
    font-weight: bold;
    border: none;
    box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;;
    border-radius: 5px;
    padding: 10px;
    margin: 25px;
}
button:hover{
    color: #E86252;
}
</style>