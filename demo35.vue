<template>
    <ol>
   
      <li :foot="foot" is="vue:my-item" v-for="(item,index) in items" :item="item"></li>
     </ol>
   </template>
   
   <script setup>
   import {ref} from 'vue'
     import MyItem from './MyItem.vue'
     const items = [{
       title:'111111'
     },{
       title:'2222'
     }]
     const foot = ref('foot')
   </script>
   <!-- 
      <my-item :foot="foot" v-for="(item,index) in items " :item="item"></my-item>
   <li is="vue:my-item" v-for=(item,index) in items :title="item"></li>
   -->
   