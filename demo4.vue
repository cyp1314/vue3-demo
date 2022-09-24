<template>
    {{state.count}}
      {{n}}
      <button @click="nadd">
        ++
      </button>
    </template>
    
    <script setup>
    
      import {reactive} from 'vue'
      const state = reactive({
        count: 0
      })
      let n = state.count
      function nadd(){
        n++
      }
    </script>