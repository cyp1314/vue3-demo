<template>
    <input ref="ipt" v-model="name" type="text" />
  </template>
  
  <script setup lang='ts'>
  
    import {ref,watchEffect} from 'vue'
    const name = ref("")
    const ipt = ref(null)
    
    watchEffect(()=>{
      if(ipt.value){
        ipt.value.focus()
      }else{
        // 此时还未挂载，或此元素已经被卸载（例如通过 v-if 控制）
      }
    })
    
  </script>