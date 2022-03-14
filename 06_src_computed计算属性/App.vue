<template>
  <div>姓: <input type="text" v-model="person.firstName" /></div>
  <div>名: <input type="text" v-model="person.lastName" /></div>
  <div>全名: {{ person.fullName }}</div>
  <div>全名: <input type="text" v-model="person.fullName" /></div>
</template>

<script>
import { reactive, computed } from 'vue'
export default {
  name: 'App',
  setup() {
    const person = reactive({
      firstName: '张',
      lastName: '三',
    })
    // 只读，不考虑修改
    // person.fullName = computed(() => {
    //   return `${person.firstName}-${person.lastName}`
    // })

    person.fullName = computed({
      get() {
        return `${person.firstName}-${person.lastName}`
      },
      set(value) {
        const arr = value.split('-')
        person.firstName = arr[0]
        person.lastName = arr[1]
      },
    })

    return {
      person,
    }
  },
}
</script>
