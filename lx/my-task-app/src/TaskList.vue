<template>
  <!-- TaskList 组件的模板 -->
  <div>
    <!-- 引入 AddTask 子组件，并监听 add-task 事件 -->
    <!-- 当事件发生时，调用 addNewTask 方法 -->
    <add-task @add-task="addNewTask"></add-task>

    <!-- 循环渲染任务列表 -->
    <ul>
      <li v-for="task in tasks" :key="task">{{ task }}</li>
    </ul>
  </div>
</template>

<script>
// 导入 AddTask 子组件
import AddTask from './AddTask.vue';

export default {
  components: {
    // 在 components 对象中注册 AddTask 组件
    AddTask
  },
  data() {
    return {
      // tasks 数组用于存储任务列表
      tasks: ['Task 1', 'Task 2']
    };
  },
  methods: {
    // addNewTask 方法用于添加新任务到任务列表
    addNewTask(newTask) {
      this.tasks.push(newTask);
    }
  }
}
</script>
