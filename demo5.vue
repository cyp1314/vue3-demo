<template>
    {{obj.foo}}--{{obj.bar}}
      <button @click="add(obj,'2')">
        ++
      </button>
      {{obj.bar}}
    </template>
    
    <script setup lang='ts'>
    import { ref,Ref  } from 'vue'
    const obj ={
      foo:ref(0),
      bar:ref(0)
    }
    function add(obj,step:number){
      obj.foo.value+=step
      obj.bar.value+=step
    }
    const object = { foo: ref(1) }
    const {foo} = object
    </script>