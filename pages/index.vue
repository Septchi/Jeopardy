<template>
    <Question v-if="asking" :question="questions[current]"/>
    <h1 class="text-6xl text-center mb-4 font-serif">Jeopardy</h1>
    <div class="flex justify-between mx-8">
        <div id="players">
            <School v-for="name in schools" :name="name"/>
        </div>
        <div id="grid" class="border-black border-4">
            <h1 v-for="name in categories" class="border-black border-2 text-2xl text-center text-white">{{name}}</h1>
            <Block v-for="(obj, n) in questions" :point="points[Math.floor(n/5)]" :answer="obj.answer"
                   @click="setCurrent(n)"/>
        </div>
    </div>
</template>

<script>
    import Block from './components/Block.vue'
    import School from './components/School.vue'
    import Question from './components/Question.vue'
    import json from './data/questions.json'
    export default {
        data() {
            var temp = [];
            var columns = 5;
            var rows = 10
            for(let i = 0; i < columns*rows; i++){
                temp.push(json.questions[(i%columns)*rows + Math.floor(i/columns)]);
                
            }
            return {
                asking: false,
                current: 0,
                categories: ["Biology & Chemistry", "Algebra & Combinatorics", "History of DOST", "Earth Science & Physics", "Geometry & Trigonometry"],
                points:[100, 100, 200, 200, 200, 200, 200, 600, 300, 1000],
                schools: ["Team 1", "Team 2", "Team 3", "Team 4"],
                questions: temp,
            }
        },
        provide(){
            return {
                toggle: ()=>{
                    this.asking = !this.asking;
                }
            }
        },
        methods: {
            setCurrent(num){
                this.current = num;
                this.asking = true;
            }
        },
    }
</script>

<style>
body {
    background-color: navy;
}
#grid {
    display: inline-grid;
    width: 75%;
    grid-template-columns: repeat(5, 1fr);
    /*gap: 8px;*/
} 
#players {
    display: flex;
    flex-direction:  column;
    width: 15%;
} 
</style>
