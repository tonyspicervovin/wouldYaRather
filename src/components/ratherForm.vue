<template>
<div>
    
        {{question.question}}
        <br>
        <input type="radio" v-model="choice" v-bind:value="question.answer1" v-on:change="$emit('answer-changed',choice)">
        <label>{{question.answer1}}</label>
        <input type ="radio" v-model="choice" v-bind:value="question.answer2" v-on:change="$emit('answer-changed',choice)">
        <label>{{question.answer2}}</label>
        <br>
        
    


</div>

</template>



<script>

export default {
    name: 'ratherForm',
    data(){
            return { choice: ''}
            },
                props: {
                 question: Object
                },

}
</script>


