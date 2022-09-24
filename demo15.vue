<template>
    <ul>
      
      <li v-for="item in items">
      {{ item.message }}
    </li>
      </ul>
      
      <hr>
      <li v-for="(item, index) in items">
      {{ parentMessage }} - {{ index }} - {{ item.message }}
    </li>
    </template>
    
    <script setup>
    import {ref} from 'vue'
    
      
      const parentMessage = ref('Parent')
    const items = ref([{ message: 'Foo' }, { message: 'Bar' }])
    
    </script>