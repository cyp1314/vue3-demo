<script setup>
    import { ref, onMounted,isRef } from 'vue'
    import Child from './Child.vue'
    import Comp from './Comp.vue'
    const child = ref(null)
    
    const comp = ref(null)
    
    
    onMounted(() => {
      // child.value 是 <Child /> 组件的实例
      console.log('child',child.value.name)
      console.log('comp1',isRef(comp))
      console.log('comp2', isRef(comp))
    })
    </script>
    
    <template>
      <Child ref="child" />
        <Comp ref="comp" />
    </template>


<script setup>
    import { ref } from 'vue'
    
    const a = 1
    const b = ref(2)
    
    defineExpose({
      a,
      b
    })
    </script>
    <template>
    <h4>
      Comp
      </h4>
    </template>



<template>
    <h2>
      hello
      </h2>
      <button @click="change">
        改变文字
      </button>
    </template>
    <script>
      import {ref} from 'vue'
    export default{
      name:'child',
      setup(){
        const name = ref('xx')
        const change = () =>{
          $emit('xx',name.value)
        }
        return {
          name,
          change
        }
      }
    }
    </script>