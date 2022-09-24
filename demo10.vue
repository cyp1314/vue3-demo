<template>
    <div :class="classobj">111</div>
    
    </template>
    
    <script setup>
    import {ref,computed,reactive} from 'vue'
      const isActive = ref(true)
    const error = reactive({
      type:'fatal'
    })
    const classobj = computed(()=>{
      return {
         active: isActive.value && !error.value,
      'text-danger':  error.type === 'fatal'
      }
    })
    </script>