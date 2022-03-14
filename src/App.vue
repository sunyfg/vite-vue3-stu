<template>
  <h1>Vue2 响应式</h1>
  <h2 v-show="person.name">姓名：{{ person.name }}</h2>
  <h2>年龄：{{ person.age }}</h2>
  <h2 v-show="person.sex">性别：{{ person.sex }}</h2>
  <button @click="addSex">添加一个 sex 属性</button>
  <button @click="deleteName">删除 name 属性</button>
</template>

<script>
import { ref, reactive } from 'vue'
export default {
  name: 'App',
  data() {
    return {
      person: {
        name: '张三',
        age: 18,
      },
    }
  },
  methods: {
    addSex() {
      this.person.sex = '男'
      console.log(this.person)
    },
    deleteName() {
      delete this.person.name
      console.log(this.person)
    },
  },
}
</script>
