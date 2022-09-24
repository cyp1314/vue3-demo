// 动态插槽
<script setup>
    import {useAttrs,onMounted} from 'vue'
      const attrs = useAttrs()
      onMounted(()=>{
        console.log('name:',attrs.name)
      })
    </script>
    
    <template>
    <div class="fancy-btn">
      <slot name="header">header</slot>
       <slot name="main">main</slot>
       <slot name="foot">foot</slot>
    </div>
    </template>

<script setup>
    import {ref} from 'vue'
    import Comp from './Comp.vue'
    const main = ref("main")
    const change = () =>{
      main.value = "foot"
    }
  </script>
  
  <template>
  <Comp title="title" name="name">
  <template #[main]>
    my main
    </template>
    </Comp>
    
    <button @click="change">
      change
    </button>
  </template>
  