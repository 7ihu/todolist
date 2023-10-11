<template>
  <form @submit.prevent="confirm">
    <div class="input-group mb-3">
      <input type="text" class="form-control" placeholder="请输入任务信息" aria-label="Recipient's username"
        aria-describedby="button-addon2" v-model.trim="value">
      <button class="btn btn-outline-secondary" type="submit" id="button-addon2">确定</button>
    </div>
  </form>
</template>

<script>
export default {
  name: 'TodoInput',
  components: {},

  data() {
    return {
      value: ''
    }
  },
  emits: ['parameter'],
  methods: {
    confirm() {
      if (this.value === '') return alert('不能为空！')
      this.$emit('parameter', this.value)
      this.value = ''
    }
  },

  watch: {},

  computed: {},

  filters: {}

}
</script>

<style lang='less' scoped></style>