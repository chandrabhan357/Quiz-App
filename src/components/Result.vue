<template>
    <div class="result" v-for="result in results">
        <div class="title" v-if="totalCorrect<= result.max">You got sample result 1!</div>
        <div class="desc">
            Enter a short description here about the result.
        </div>
    </div>
</template>

<script>
    export default {
        props:['results', 'totalCorrect'],
    }
</script>

<style scoped>

</style>