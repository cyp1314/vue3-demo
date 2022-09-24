<template>
    <ul>
        <li v-for="item in list" ref="itemRefs">
          {{ item }}
        </li>
      </ul>
    </template>
    
    <script setup lang='ts'>
    
    import { ref, onMounted } from 'vue'
    const itemRefs = ref([])
    onMounted(() => {
      itemRefs.value.forEach(x=>{
        if(x.innerText == "2"){
          x.style.color = "green"
        }else{
          x.style.color = "red"
        }
      })
    })
      const list = [1,2,3]
    </script>