<template>
    {{hello}}<br>
    <button @click="changeStr">
      update
    </button>
  </template>
  <script setup>
  import {ref,inject} from 'vue'
    
    const {hello,changeStr} = inject('par')
  </script>
  // 父组件
  <script setup>
    import Comp from './Comp.vue'
  import { provide,ref } from 'vue'
    const hello = ref('hello')
  
  // provide('hello',hello)
    const changeStr = () => {
      hello.value ='xxx'
    }
    provide('par',{
      hello,
      changeStr
    })
  </script>
  
  <template>
  <Comp></Comp>
  </template>