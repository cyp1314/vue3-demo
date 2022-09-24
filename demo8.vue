<template>
    <span ref="span">{{vu}} --> {{vuComputed}}</span>
    <button @click="change">
      click
    </button>
  </template>
  
  <script setup>
  import {ref,computed} from 'vue'
    const vu = ref('xxx')
  
    const vuComputed = computed(()=>{
           vu.value='ooo'
      return vu
      setTimeout(()=>{
            console.log('uv change')
       vu.value='ooo'
      return vu
      },5000)
    })
    const change = ()=>{
      vu.value="..."
    }
  </script>