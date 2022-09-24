<template>
    数字：{{num}}
    <button @click="add">
      +1
    </button>
  </template>
  
  <script setup lang='ts'>
  
    import {ref,watch} from 'vue'
    const num = ref(0)
      const num2 = ref(0)
    const add = () =>{
      num.value+=1
    }
    // 直接侦听ref对象
    watch(num,(newV,oldV)=>{
     console.log(newV,'-',oldV) 
    })
    // 侦听getter函数
    watch(
    ()=>num.value,
      (n,o)=>{
        console.log(n,'-->',o) 
      }
    )
    // 侦听多个
    watch([num,num2],([numn,num2n],[numo,num2o])=>{
      console.log(numn,'-->>>',numo) 
       console.log(num2n,'-->>>',num2o) 
    })
  </script>