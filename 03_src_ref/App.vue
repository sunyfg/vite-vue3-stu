<template>
  <h1>姓名：{{name}}</h1>
  <h2>年龄：{{age}}</h2>
  <h2>工作：{{job.type}}</h2>
  <h2>薪水：{{job.salary}}K</h2>
  <button @click="changeInfo">修改信息</button>
</template>

<script>
import { ref } from 'vue'
export default {
  name: 'App',
  setup() {
    let name = ref('张三')
    let age = ref(20)
    let job = ref({
      type: '前端',
      salary: 30
    })

    function changeInfo() {
      // name = '李四'
      // age = 30
      // job.type = 'UI 设计师'
      // job.salary = 60
      console.log(name, age);
    }

    // 返回一个对象
    return {
      name,
      age,
      job,
      changeInfo
    }
  }
}
</script>
