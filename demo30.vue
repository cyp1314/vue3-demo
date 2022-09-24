<template>
    <h2>welcome</h2>
    <hr>
    <button @click="change('1')">
      com1
    </button>
      <button @click="change('2')">
      com2
    </button>
    <component :is="ck"></component>
  </template>
  
  <script setup>
    import {ref,shallowRef} from 'vue'
    import Com1 from './Comp1.vue'
    import Com2 from './Comp2.vue'
    
    const tabs = {
      Com1,
      Com2
    }
  let ck = shallowRef()
    
  function change(x){
      switch(x){
        case '1':
         ck.value = tabs.Com1
        break;
        case '2':
         ck.value = tabs.Com2
        break
      }
    console.log('ck:',ck.value)
    }
    </script>