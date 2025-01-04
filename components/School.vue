<template>
    <div id="tile" class="border-black border-4 rounded-2xl" @click="this.hidden = !this.hidden">

        <h1 class="w-1/2 mx-auto text-center">{{name}}</h1>
        <input type="text" value="0" class="text-center text-white bg-blue-500 rounded-lg w-3/4 mx-auto">
    </div>
</template>

<script>
    export default{
        data() {
            return {
                point: 0,
            }
        },
        props: {
            name: {
                type: String,
                default: "bobo"
            }
        },
    }
</script>

<style scoped>
#tile {
    margin: 5px auto;
    display: flex;
    flex-direction: column;
    background-color: salmon;
    height: 100px;
    width: auto;
    justify-content: center;
}
</style>
