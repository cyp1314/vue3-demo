<template>
    <p>
        Ask a yes/no question:
        <input v-model="question" />
      </p>
      <p>{{ answer }}</p>
    </template>
    
    <script setup lang='ts'>
    import { ref, watch } from 'vue'
    const question = ref('')
    const answer = ref('Questions usually contain a question mark. ;-)')
    
    // 直接侦听一个ref
    watch(question, async   (newQuestion, oldQuestion)=>{
      if(newQuestion.indexOf('?') > -1){
        answer.value = 'Thinking...'
      }
      try{
        setTimeout(()=>{
          answer.value = 'xxxxx'
        },5000)
      }catch(error){
        answer.value = 'Error! Could not reach the API. ' + error
      }
    })
    </script>