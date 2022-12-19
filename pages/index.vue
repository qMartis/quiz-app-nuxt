<template>
    <div class="w-screen h-screen bg-gray-100 flex items-center">
        <Question v-if="current_question <= questions.length-1" @on-answer-selected="answerSelected" @on-next-question="current_question++" :question="questions[current_question]"/>
        <Results v-else :questions="questions"/>
    </div>
</template>
<script>
export default {
    data() {
        return {
            current_question: 0, //index
            questions: [
                {
                    title: 'What is CSS?',
                    correct_answer: 0, // index of array
                    selected_answer: null, //index of answers array
                    answers: [
                        'This is a web styling lang', // 0
                        'A car part', // 1
                        'This is sweat cake', // 2
                    ],
                },
                {
                    title: 'What is HTML?',
                    correct_answer: 1, // index of array
                    selected_answer: null, //index of answers array
                    answers: [
                        'Town', // 0
                        'Hyper text markup lang', // 1
                    ],
                },
                {
                    title: 'Is PHP compilable ?',
                    correct_answer: 1, // index of array
                    selected_answer: null, //index of answers array
                    answers: [
                        'True', // 0
                        'False', // 1
                    ],
                }
            ],
        }
    },

    methods: {
        answerSelected( index ) {
            if(this.questions[this.current_question].selected_answer != null) return false;
            this.questions[this.current_question].selected_answer = index
        }
    }
}
</script>