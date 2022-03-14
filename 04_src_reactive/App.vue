<template>
  <h1>姓名：{{ person.name }}</h1>
  <h2>年龄：{{ person.age }}</h2>
  <h2>工作：{{ person.job.type }}</h2>
  <h2>薪水：{{ person.job.salary }}K</h2>
  <h2>爱好：{{ person.hobby }}</h2>
  <h2>测试数据：{{ person.job.a.b.c }}</h2>
  <button @click="changeInfo">修改信息</button>
</template>

<script>
import { ref, reactive } from 'vue'
export default {
  name: 'App',
  setup() {
    let person = reactive({
      name: '张三',
      age: 20,
      job: {
        type: '前端',
        salary: 30,
        a: {
          b: {
            c: 111,
          },
        },
      },
      hobby: ['音乐', '电影', '登山'],
    })

    function changeInfo() {
      console.log(person)
    }

    // 返回一个对象
    return {
      person,
      changeInfo,
    }
  },
}
</script>
