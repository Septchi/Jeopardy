<template>
    <div id="popup">
        <div id="inner" @click="toggle">
            <h1 class="text-xl font-semibold text-center">{{type}}</h1>
            <h1 class="m-4 h-4/6">{{!show ? body : answer}}</h1>
            <buton @click.stop="show = true" class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-blue-300 font-medium rounded-lg
                text-sm px-5 py-2.5 me-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800 
                mx-4">Show Answer</buton>
        </div>
    </div>
</template>

<script>
    export default{
        data() {
            return {
                show: false
            }
        },
        props: {
            question: Object
        },
        computed: {
            body(){
                return this.question.body
            },
            type(){
                return this.question.category
            },
            answer(){
                return this.question.answer
            }
        },
        inject: ['toggle'],
    }
</script>

<style scoped>
 #popup {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    z-index: 10;
    background-color: rgba(0, 0, 0, 0.45);
    display: flex;
    justify-content: center;
    align-content: center;
 }
 #inner{
     background-color: whitesmoke;
     margin: auto;
     height: 50%;
     width: 30%;
 }
</style>
