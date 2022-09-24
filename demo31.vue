<script setup>
    import { ref } from 'vue'
    const message = ref('Hello World!')
    function reverseMessage(){
      message.value = message.value.split('').reverse().join('')
    }
     function append(){
       message.value+='!'
     }
      function notify(){
        alert('1')
      }
    </script>
    
    <template>
      <h1>{{ message }}</h1>
      <button @click="reverseMessage">
        reverseMessage
      </button>
        <button @click="append">
        appenend !
      </button>
       <a href="https://vuejs.org" @click.prevent="notify">
        A link with e.preventDefault()
      </a>
      
    </template>