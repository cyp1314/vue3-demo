<template>
    <ul>
      <li v-for="(value, key ,index) in myObject">
        {{ value }} -- {{key}} -- {{index}}
      </li>
    </ul>
    </template>
    
    <script setup>
    import {ref,reactive} from 'vue'
      const myObject = reactive({
      title: 'How to do lists in Vue',
      author: 'Jane Doe',
      publishedAt: '2016-04-10'
    })
    
    </script>