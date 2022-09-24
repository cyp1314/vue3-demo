<template>
    <div>
      {{abj.name}}--{{abj.age}} 
    </div>
    <div>
      {{book.title}}--{{book.year}}
    </div>
    <div>
      <button @click="increment">
        {{number.count}}
      </button>
    </div>
  </template>
  <script setup lang='ts'>
  import {reactive} from 'vue'
  const abj = reactive({
    name:'李白',
    age:12
  })
  interface IBook {
    title:string
    year?:number
  }
    const book:IBook = reactive({
      title:'vue3',
      year:2002
    })
    
    const number = reactive({
      count:0
    })
    function increment(){
      number.count++
    }
  </script>