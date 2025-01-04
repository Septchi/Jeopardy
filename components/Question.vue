<template>
    <div id="popup">
        <div id="inner" @click="toggle">
            <h1 class="text-xl font-semibold text-center">{{type}}</h1>
            <h1 class="m-4">{{body}}</h1>
        </div>
    </div>
</template>

<script>
    export default{
        props: {
            body: {
                type: String,
                default: "Warap"
            },
            type: {
                type: String,
                default: "Meth"
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
