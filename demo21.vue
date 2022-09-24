<template>
    obj.count:{{obj.count}}
      <button @click="change">
        改变count
      </button>
    </template>
    
    <script setup lang='ts'>
    
      import {watch,reactive} from 'vue'
    
      const obj = reactive({
        count:0
      })
      const change = ()=>{
        obj.count+=1
      }
      watch(()=>obj.count,(n,o)=>{
        console.log(n,'->',o)
      })
    </script>