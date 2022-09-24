<template>
    <p>
      {{content}}
    </p>
    <p :class="{redStyle:isCheck}" @click="changeColor">
      {{toggle}}
    </p>
    <p :class="[{redStyle:isCheck},'blueStyle']"  @click="changeColor">
      This should be green, and should toggle between green and blue on click.
    </p>
  </template>
  
  <script setup>
  import {ref} from 'vue'
    const content = ref('Hover your mouse over me for a few seconds to see my dynamically bound title!')
    const toggle = ref('This should be red... but click me to toggle it.')
    const isCheck = ref(false)
    function changeColor(){
      isCheck.value =! isCheck.value
    }
  </script>
  
  <style>
    .redStyle{
      color:red !important;
    }
    .blueStyle{
      color:blue;
    }
  </style>