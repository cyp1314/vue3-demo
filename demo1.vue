<template>
    <div id='app'>
    <span>msg:{{msg}}</span>
  <div v-html='html_msg'></div>
    <div v-bind:id='test' v-bind:name1='name1'>
      Attribute 绑定
    </div>
    <button :disabled="isButtonDisabled">Button</button>
    <div v-bind="objectOfAttrs">动态绑定多个值</div>
    
      <div :="objectOfAttrs">动态绑定多个值1</div>
    {{ number + 1 }}
  
  {{ ok ? 'YES' : 'NO' }}
  全局数据:{{Math.random(1)*10}}
  {{ message.split('').reverse().join('') }}
  
  <div :id="`list-${id}`">111</div>
  <span :title="toTitleDate(date)">
    {{ formatDate(date) }}
  </span>
    <p v-if="seen">Now you see me</p>
  <a v-bind:href="url"> ...1 </a>
    <a :href="url"> ...2 </a>
      
      <a v-on:click="doSomething"> ... </a>
  
  <!-- 简写 -->
  <a @click="doSomething"> ... </a>
       <div ref="el"></div>
    </div>
  
    <a :[attr]="url">动态参数1</a>
     <img width="10" height="10" v-bind:[add]="address" :="xz"/>
    <button v-on:click.prevent="test1">
      指令顺序
    </button>
  </template>
  
  <script setup>
  
  import {ref,onMounted,reactive,createApp} from 'vue'
    const el = ref()
    const ok = ref(1)
    const attr = ref('href')
    const msg = ref('hello')
    const html_msg = ref('<span style="color:red">aaa</span>')
    const test = ref('my-id')
    const name1 = ref(null)
    const message = ref('hello')
    const date = ref('xxx1')
    const id = ref(0)
    const isButtonDisabled = ref('a') // 0:false 1:true  '':true 'a':true
    const objectOfAttrs = reactive({
    id: 'container',
    class: 'wrapper'
  })
    const xz = reactive({
  width:20,
      height:20
    })
    const url = ref('#')
    const add = ref('src')
    const address = '/logo.svg'
    const seen = ref(1)
      const number = ref(0)
    onMounted(()=>{
     console.log('>>>:', el.value)
      setTimeout(()=>{
        objectOfAttrs.id='xxx'
        name1.value="a"
        console.log('timeout')
      },5000)
    })
       
      const toTitleDate  =   (dd) =>{
        return dd
      }
      const formatDate  =   (dd) =>{
        return dd
      }
      const doSomething =(dd)=>{
        
      }
          const test1 =(dd)=>{
        alert('a')
      }
  </script>
  <style>
    #my-id{
      color:green;
    }
  </style>