<template>
    <div id="tile" class="border-black border-2" @click="this.hidden = !this.hidden">
        <p :class="{'text-center m-auto text-[#FFFF00] shadow-inner':true, 'text-2xl':hidden, 'text-lg':!hidden}">{{text}}</p>
    </div>
</template>

<script>
    export default{
        data() {
            return {
                hidden : true,
            }
        },
        props: {
            point: {
                type: Number,
                default: 3,
            },
            answer: {
                type: String
            }
        },
        computed: {
            text(){
                return this.hidden ? this.point : ""
            }
        },
    }
</script>

<style scoped>
#tile {
    background-color: cornflowerblue;
    height: 45px;
    width: auto;
    display: flex;
}
</style>
