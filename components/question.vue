<template>
    <div class="m-auto max-w-2xl bg-white p-5 grid text-center">
        <h1 class="text-xl mb-3">{{ question.title }}</h1>
        
        <button @click="$emit('onAnswerSelected', index)" 
        class="mb-2 w-full py-3 bg-gray-100 px-10"
        :class="{' bg-green-300' : question.selected_answer != null && index == question.correct_answer },
        {' bg-red-400' : question.selected_answer != question.correct_answer && index == question.selected_answer },
        {' hover:bg-gray-300' : question.selected_answer == null }"
         v-for="(answer, index) in question.answers" :key="answer">{{ answer }}</button>
        
        <button 
        @click="$emit('onNextQuestion', index)" 
        v-show="question.selected_answer != null" class="mt-4 w-full py-3 bg-blue-500 text-white">Next question -></button>
    </div>
</template>

<script>
export default {
    props: ['question'],
}
</script>