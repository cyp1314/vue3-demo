<template>
    <div
      class="static"
      :class="{ active: isActive, 'text-danger': hasError }"
    >111</div>
      
      <div :class="classobj">
        222
      </div>
    </template>
    
    <script setup>
    import {ref,reactive} from 'vue'
      const isActive = ref(true)
    const hasError = ref(true)
    const classobj = reactive({
      'redfont':true,
      'fontsize':true
    })
    </script>
    
    <style>
      .active{
        color:red;
      }
      .text-danger{
        font-size:32px
      }
      .redfont{
         color:red;
      }
      .fontsize{
        font-size:32px
      }
    </style>