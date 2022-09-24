<template>
    <input ref="ipt" v-model="name" type="text" />
  </template>
  
  <script setup lang='ts'>
  
    import {ref,onMounted} from 'vue'
    const name = ref("")
    const ipt = ref(null)
    onMounted(()=>{
      ipt.value.focus()
    })
    
  </script>