<template>
  <button @click="isShow = !isShow">切换显示/隐藏</button>
  <Demo v-if="isShow" />
</template>

<script>
import { ref } from 'vue'
import Demo from './components/Demo.vue'
export default {
  name: 'App',
  components: { Demo },
  setup(props) {
    let isShow = ref(true)

    return { isShow }
  }
}
</script>
