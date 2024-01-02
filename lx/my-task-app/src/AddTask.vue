<template>
  <!-- AddTask 组件的模板 -->
  <div>
    <!-- 文本输入框，用于输入新任务 -->
    <!-- 使用 v-model 双向绑定 newTask 数据属性 -->
    <input v-model="newTask" @keyup.enter="submitTask">
    <!-- 添加任务按钮，点击时调用 submitTask 方法 -->
    <button @click="submitTask">Add Task</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // newTask 用于存储输入框的值
      newTask: ''
    };
  },
  methods: {
    // submitTask 方法用于处理新任务的提交
    submitTask() {
      // 触发 add-task 事件并将新任务作为参数传递
      this.$emit('add-task', this.newTask);
      // 清空输入框
      this.newTask = '';
    }
  }
}
</script>
