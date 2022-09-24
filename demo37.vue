// 子组件
<template>
    <input v-model="value" />
    </template>
    
    <script setup>
    import {computed} from 'vue'
     const props = defineProps(['msg'])
     const emit = defineEmits(['update:msg'])
    const value = computed({
      get(){
        return props.msg
      },
      set(value){
        emit('update:msg',value)
      }
    })
    </script>

    // 父组件
    <template>
        <Comp v-model:msg="msg"></Comp>{{msg}}
      </template>
        
      <script setup>
      
        import {ref} from 'vue'
        import Comp from './Comp.vue'
        const msg = ref('hello')
      </script>