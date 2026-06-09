  <script setup lang="ts">
  import { ref } from 'vue'

  const count = ref(0)
  const increment = () => count.value++
  </script>

  <template>
    <div>
      <p>当前计数：{{ count }}</p>
      <button @click="increment">+1</button>
    </div>
  </template>