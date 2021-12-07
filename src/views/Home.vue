<template>
  <div class="antialiased text-gray-700 bg-gray-100">
    <div class="flex w-full h-screen justify-center items-center">
      <div class="w-full max-w-xl">
        <h1 class=" font-bold text-5xl text-center text-indigo-700">
          Simple Quiz
        </h1>
        <question :title="questions[0]['question']" :choices="questions[0]['incorrect_answer'].map(a=>a)"></question>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import Question from "../components/Question.vue"
export default {
  name: 'Home',
  components:{
    Question
  },
  mounted(){
    axios.get('https://opentdb.com/api.php?amount=10&difficulty=hard&type=multiple').then((res) => {
      this.questions = res.data.results
    })
  },
  data(){
    return{
      questions: [],
      selectedAns: "",
    }
  },
};
</script>
