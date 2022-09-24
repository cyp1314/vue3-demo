<template>
    <div :class=[a1,a2]>
      111
    </div>
      <div :class=[isActive?a1:a2,all_class]>
      222
    </div>
    <div :style="{ color: activeColor, fontSize: fontSize + 'px' }">333</div>
    <div :style="{ 'font-size': fontSize + 'px' }">444</div>
  
    <div :style=styleObject>444</div>
     <div :style=styleComputed>555</div>
       <div :style="[ac1,ac2]">666</div>
  </template>
  
  <script setup>
  import {ref,reactive,computed} from 'vue'
    const a1 = ref('active')
      const a2 = ref('text-danger')
      const isActive = ref(null)
      const all_class = ref('f16')
      const activeColor = ref('red')
  const fontSize = ref(30)
  const styleObject = reactive({
    color: 'green',
    fontSize: '32px'
  })
  const styleComputed = computed(()=>{
    return {
      color: 'yellow',
    fontSize: '32px'
    }
  })
  const ac1 = reactive({
    color:'blue'
  })
  const ac2 = reactive({
    fontSize:'32px'
  })
  </script>
  
  <style>
    .f16{
      font-size:15px;
        font-weight:bolder
    }
  </style>