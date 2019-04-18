<template>
  <div id="app">
    <ratherForm 
    v-for="question in questions" 
    v-bind:key="question.question"
    v-bind:question="question"
    v-on:answer-changed="answerChanged">>
    </ratherForm>
    <ratherCSS>
      
    </ratherCSS>
    <ratherScript
      v-bind:message="userSelectionMessage"
      >
    </ratherScript>
  </div>
</template>

<script>
import ratherForm from './components/ratherForm.vue'
import ratherScript from './components/ratherScript.vue'
import ratherCSS from './components/ratherCSS.vue'

export default {
  name: 'app',
  data(){
    return{
      userSelectionMessage: '',
      questions: [
        {
          id: 0,
          question:'Would you rather be able to do flips and backflips or break dance?',
          answer1: 'Flips',
          answer2: 'Break dance',

        },
        {
          id:1,
          question: 'Would you rather fly a kite or swing on a swing?',
          answer1: 'Kite',
          answer2: 'Swing',
        },
        {
          id:2,
          question: 'Would you rather be a wizard or a superhero?',
          answer1: 'Wizard',
          answer2: 'Superhero',
        }
      ]
    }

  },
  components: {
    ratherForm,
    ratherScript,
    ratherCSS
  },
  methods: {
    answerChanged(answer){
                    console.log(`I changed to ${answer}`)

                    this.userSelectionMessage = `Thanks! you selected ${answer}`
                }
  }

  
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
