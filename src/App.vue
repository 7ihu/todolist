<template>
  <div>
    <h1>TodoList</h1>
    <hr>
    <TodoInput @parameter="reception"></TodoInput>
    <hr>
    <TodoList :todolist="todolist"></TodoList>
  </div>
</template>

<script>
import TodoList from './components/todolist/TodoList.vue'
import TodoInput from './components/todoInput/TodoInput.vue'


export default {
  name: 'App',
  components: {
    TodoList,
    TodoInput
  },

  data() {
    return {
      todolist: [
        { id: 1, task: '周一早晨9点开会', done: false },
        { id: 2, task: '周晚上8点聚餐', done: false },
        { id: 3, task: '准备周三上午的演讲稿', done: true },
      ],
      nextId: 4
    }
  },
  // created() {
  //   this.color()
  // },

  methods: {
    reception(value) {
      this.todolist.push({ id: this.nextId, task: value, done: false })
      this.nextId++
    },
  },

  watch: {},

  computed: {},

  filters: {},
}
</script>

<style lang="less" scoped>
div {
  h1 {
    text-align: center;
  }
}
</style>
