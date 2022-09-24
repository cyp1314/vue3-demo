// 子组件
<template>
    <input type="text" :value="modelValue" @input="$emit('update:modelValue',$event.target.value)" />
  </template>
  
  <script setup>
    defineEmits(['update:modelValue'])
    defineProps(['modelValue'])
  </script>

  // 父组件
  <template>
    <Comp v-model="msg"></Comp>{{msg}}
  </template>
    
  <script setup>
  
    import {ref} from 'vue'
    import Comp from './Comp.vue'
    const msg = ref('hello')
  </script>

  // 其他方式
  <template>
    <input v-model="value" />
    </template>
    
    <script setup>
    import {computed} from 'vue'
     const props = defineProps(['modelValue'])
     const emit = defineEmits(['update:modelValue'])
    const value = computed({
      get(){
        return props.modelValue
      },
      set(value){
        emit('update:modelValue',value)
      }
    })
    </script>