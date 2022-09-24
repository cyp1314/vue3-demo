/** v-on 监听器继承 */
// 组件
<template>
    <button @click="emitHandler">
      测试
      </button>
    </template>
    
    <script setup>
    const emit = defineEmits(['emitHandler'])
    const emitHandler = () =>{
      emit('emitHandler')
    }
    </script>
// 父组件
<script setup>
    import {ref} from 'vue'
    import Comp from './Comp.vue'
    const hander1 = () =>{
      console.log('hander1')
    }
      const selfHander = () =>{
      console.log('selfHander')
    }
  </script>
  
  <template>
  <Comp @emitHandler="hander1" @click="selfHander"></Comp>
  </template>