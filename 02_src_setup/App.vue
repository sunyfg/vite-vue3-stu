<template>
  <h1>姓名：{{name}}</h1>
  <h2>年龄：{{age}}</h2>
  <button @click="say">说话</button>
</template>

<script>
import { h } from 'vue'
export default {
  name: 'App',
  setup() {
    let name = '张三'
    let age = 20

    function say() {
      console.log(`你好，我叫${name}，我${age}岁了。`)
    }

    // 返回一个对象
    return {
      name,
      age,
      say
    }

    // 返回一个渲染函数
    /* return () => h('h1', `你好，我叫${name}，我${age}岁了。`) */
  }
}
</script>
