<template>
  
    <!-- 有 index 索引时 -->
    <li v-for="({ a }, index) in items">
      {{ a }} {{ index }}
    </li>
    </template>
    
    <script setup>
    import {ref} from 'vue'
      const parentMessage = ref('Parent')
    const items = ref([{ a: 'Foo' }, { a: 'Bar' }])
    </script>