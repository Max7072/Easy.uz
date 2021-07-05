<template>
<div>
    <Sparkline id="sparkline"/>
    <Question/>
</div>

</template>

<script>
import Sparkline from '@/components/sparkline.vue'
import Question from '@/components/question.vue'

export default {
    components: {
        Sparkline,
        Question,
        
    },  
}
</script>

<style scoped>
    #sparkline{
        top: 100px;
    }
</style>