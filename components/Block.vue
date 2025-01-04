<template>
    <div id="tile" class="border-black border-4 rounded-2xl" @click="this.hidden = !this.hidden">
        <p :class="{'text-center m-auto':true, 'text-5xl':hidden, 'text-lg':!hidden}">{{text}}</p>
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
                return this.hidden ? this.point : this.answer
            }
        },
    }
</script>

<style scoped>
#tile {
    background-color: salmon;
    height: 75px;
    width: auto;
    display: flex;
}
</style>
