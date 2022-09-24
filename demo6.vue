<template>
    <button @click="increment">{{ count }}</button>
    <div>
      <p>Has published books:</p>
      <span>{{ author.books.length > 0 ? 'Yes' : 'No' }}</span><br>
      <span>{{publishBook}}</span><br>
      {{Date.now()}}
    </div>
  </template>
  
  <script setup>
  import {ref,reactive,computed} from 'vue'
    let count = $ref(0)
  function increment() {
    // 无需 .value
    count++
  }
    const author = reactive({
    name: 'John Doe',
    books: [
      'Vue 2 - Advanced Guide',
      'Vue 3 - Basic Guide',
      'Vue 4 - The Mystery'
    ]
  })
  const publishBook = computed(()=>{
    return author.books.length > 0 ? 'Yes' : 'No'
  })
  </script>