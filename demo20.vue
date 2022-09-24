<template>
    <input v-model="name" type="text" />
  </template>
  
  <script setup lang='ts'>
  
    import {ref,watch} from 'vue'
    const name = ref('')
    
    watch(name,(n,o)=>{
      console.log('n:',n,',o:',o)
    })
  </script>