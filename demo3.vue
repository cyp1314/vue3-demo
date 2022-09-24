<template>

    <div id="app" ref="app">
      {{msg}}
    </div>
    <button @click="mutateDeeply">
      深层相应性
    </button>
    非相应：{{abc}}
  </template>
  
  <script setup>
      import {ref,reactive,onMounted,nextTick} from 'vue'
    const abc = "abc"
    const msg = ref('hello')
    const app = ref()
    const obj = reactive({
    nested: { count: 0 },
    arr: ['foo', 'bar']
  })
    function mutateDeeply() {
    // 以下都会按照期望工作
    obj.nested.count++
    obj.arr.push('baz')
      console.log(obj)
  }
    onMounted(()=>{
      setTimeout(()=>{
       nextTick(()=>{
          app.value.style.color="red"
       })
      },3000)
    })
  </script>