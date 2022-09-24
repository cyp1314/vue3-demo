<template>
    <div>
      <p>Message is: {{ message }}</p>
    <input v-model="message" placeholder="edit me" />
      </div>
      
      <div>
        <textarea v-model="textarea"></textarea>
      </div>
      
      <div>
        <h4>
          单一的复选框，绑定布尔类型值
        </h4>
        <input type="checkbox" id="checkbox" v-model="checkbox"/>
      </div>
      
      <div>
        <div>Checked names: {{ checkedNames }}</div>
    
        <input type="checkbox" id="jack" value="Jack" v-model="checkedNames">
    <label for="jack">Jack</label>
    
    <input type="checkbox" id="john" value="John" v-model="checkedNames">
    <label for="john">John</label>
    
    <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
    <label for="mike">Mike</label>
        
      </div>
      <div>
        <div>Picked: {{ picked }}</div>
    
    <input type="radio" id="one" value="One" v-model="picked" />
    <label for="one">One</label>
    
    <input type="radio" id="two" value="Two" v-model="picked" />
    <label for="two">Two</label>
    
      </div>
      <div>
        <div>Selected: {{ selected }}</div>
    
    <select v-model="selected" multiple>
      <option disabled value="">请选择</option>
      <option value="a">A</option>
      <option value="b">B</option>
      <option value="c">C</option>
    </select>
      </div>
    </template>
    
    <script setup lang='ts'>
    
      import {ref,onMounted } from 'vue'
      const message = ref('')
      const textarea = ref('请输入...')
      const checkbox = ref()
      const checkedNames = ref([])
        const picked = ref('Two')
        const selected = ref([])
    </script>