<script setup>
    import { ref, onMounted, onUnmounted } from 'vue'
      
    const x = ref(0)
    const y = ref(0)
    
    const update = e => {
      x.value = e.pageX
      y.value = e.pageY
    }
    
    onMounted(() => window.addEventListener('mousemove', update))
    onUnmounted(() => window.removeEventListener('mousemove', update))
    </script>
    
    <template>
      <slot :x="x" :y="y"/>
    </template>

    // 父组件
    <script setup>
        import MouseTracker from './MouseTracker.vue'
        </script>
        
        <template>
            <MouseTracker v-slot="{ x, y }">
              Mouse is at: {{ x }}, {{ y }}
            </MouseTracker>
        </template>