/** 获取Attrs */
// 子组件
<script setup>
    import {useAttrs,onMounted} from 'vue'
      const attrs = useAttrs()
      onMounted(()=>{
        console.log('name:',attrs.name)
      })
    </script>
    
    <template>
      <span>hello</span><br>
      {{$attrs}}
    </template>
    
    
    
    <style>
      .btn-wrapper{
        padding:10px;
        border:1px solid red;
      }
      
      .btn{
        background:green;
        border:1px solid yellow;
      }
    </style>
    // 父组件
    <script setup>
        import Comp from './Comp.vue'
      </script>
      
      <template>
      <Comp title="title" name="name"></Comp>
      </template>
      