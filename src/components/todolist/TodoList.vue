<template>
  <div>
    <ul class="list-group">
      <li class="list-group-item d-flex justify-content-between align-items-center" v-for="item in todolist"
        :key="item.id">
        <div class="form-check">
          <input class="form-check-input" type="checkbox" value="" id="item.id" v-model="item.done">
          <label class="form-check-label" :id="item.done ? 'delete' : ''" for="item.id">{{ item.task }}</label>
        </div>
        <span class="badge text-bg-success rounded-pill" v-if="item.done">已完成</span>
        <span class="badge text-bg-warning rounded-pill" v-else>未完成</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'TodoList',
  components: {},

  props: {
    todolist: {
      type: Array,
      required: true,
      default: []
    }
  },
  data() {
    return {}
  },

  methods: {
  },

  watch: {},

  computed: {},

  filters: {}

}
</script>

<style lang='less' scoped>
div {
  ul {
    width: 400px;
    margin: 0 auto;

    li {
      height: 50px;

      #delete {
        text-decoration: line-through;
        color: gray;
        font-style: italic;
      }
    }
  }
}
</style>