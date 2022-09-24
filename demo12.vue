<template>
    <h1 v-if="awesome">Vue is awesome!</h1>
    <button @click='hide'>
      {{    type }}
      </button>
    </template>
    
    <script setup>
    import {ref} from 'vue'
      const awesome = ref(true)
      const type = ref('隐藏')
      const hide = () =>{
        awesome.value= !awesome.value
        if( awesome.value){
          type.value = '隐藏'
        }else{
           type.value = '显示'
        }
    
      }
    </script>