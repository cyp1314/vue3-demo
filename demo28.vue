<template>
    <input v-if="isShow" :ref="testRef" v-model="name">
      <button @click="chenckStatus">
        显示
      </button>
    </template>
    
    <script setup lang='ts'>
    
      import {ref,nextTick} from 'vue'
      const name = ref('name')
      const isShow = ref(false)
      const testRef = (el) =>{
        console.log('进入...')
       if(el!=null){
         el.style.color="red"
         nextTick(()=>{
           isShow.value = !isShow.value
         })
       }
      }
      const chenckStatus = () =>{
         isShow.value = !isShow.value
      } 
      
    </script>