<template>
    {{fullName}}
      <button @click='changefn'>
        chage
      </button>
    </template>
    
    <script setup>
    import { ref, computed } from 'vue'
      const firstName = ref('John')
    const lastName = ref('Doe')
    // 返回值为一个计算属性 ref
    const fullName = computed({
      // getter
      get() {
        return firstName.value + ' ' + lastName.value
      },
      // setter
      set(newValue) {
        // 注意：我们这里使用的是解构赋值语法
        [firstName.value, lastName.value] = newValue.split(' ')
      }
    })
    const changefn = () =>{
      fullName.value = 'C Y'
    }
    </script>