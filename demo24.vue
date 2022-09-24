/**
* watch 是懒执行的：仅当数据源变化时，才会执行回调
* watchEffect 在创建侦听器时，立即执行一遍回调
watchPostEffect 后置刷新的 watchEffect()
*/
<template>
  <span ref="ssp" :class="{active:isActive}">{{name}}</span>
  <button @click="changeName">
    change name
  </button>
</template>

<script setup lang='ts'>

  import {ref,onMounted,watchPostEffect,watchEffect,watch} from 'vue'
  const name = ref('name')
  const isActive = ref(true)
  const ssp = ref()
  const changeName = () =>{
    name.value="yy"
  }
  onMounted(()=>{
    console.log('ssp onMounted:',ssp.value)
  })
  watch(name,()=>{
    console.log('ssp watch:',ssp.value)
  })
  
 
</script>

<style>
  .active{
    color:red;
  }
</style>