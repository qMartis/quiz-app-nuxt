<template>
    <div class="m-auto max-w-2xl bg-white p-5 grid text-center">
        <h1 class="text-xl mb-3">Results</h1>
        <div>
            Correct answers {{ questions.filter(function(item) {
                if(item.correct_answer == item.selected_answer) return true;
                return false;
            }).length }}/{{ questions.length }}
        </div>
    </div>
</template>

<script>
export default {
    props: ['questions'],
}
</script>