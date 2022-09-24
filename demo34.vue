<template>
    <h4>
     text input
      </h4>
      <input type='text' v-model="utext" /> {{utext}}
      <hr>
      <h4>
        checkbox
      </h4>
      <input type="checkbox" v-model="ucb" />
      <text>checked:{{ucb}}</text>
      <hr>
      <h4>
        Multi Checkbox
      </h4>
      <input id="jack" type="checkbox" value="jack" v-model="cks" />
      <label for="jack">jack</label>
        <input id="july" type="checkbox" value="july" v-model="cks" />
      <label for="july">july</label>
          <input id="make" type="checkbox" value="make" v-model="cks" />
      <label for="make">make</label>
      <p>
        已选择：{{cks}}
      </p>
      <hr>
      <h4>
        Radio
      </h4>
      <input id="n" type="radio" value="n" v-model="sex" />
      <label for="n">男</label>
        <input id="m" type="radio" value="m" v-model="sex" />
      <label for="m">女</label>
      <p>
        已选择:{{sex == 'n' ? '男' : '女'}}
      </p>
    </template>
    
    <script setup>
    import {ref} from 'vue'
      const utext = ref('edit text')
      const ucb = ref(false)
      const cks = ref([])
        const sex = ref()
    </script>