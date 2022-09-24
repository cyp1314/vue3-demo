<template>
    {{num}}
      <br>
      {{ck}}
    </template>
    
    <script setup lang='ts'>
    
      import {ref,watchEffect} from 'vue'
      const ck = ref('...')
      const num = ref(Math.random())
        watchEffect(async ()=>{
        if(num.value>0.3){
          ck.value = "pass"
        }else{
          ck.value = 'npass'
        }
      })
    
    </script>