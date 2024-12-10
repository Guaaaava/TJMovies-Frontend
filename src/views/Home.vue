<!-- src/views/Home.vue -->
<template>
  <div class="home">
    <h1>欢迎来到我的首页！</h1>
    <p>这是一个使用 Vue 3、TypeScript 和 Vite 构建的简单项目。</p>
    <button @click="changeMessage">点击我</button>
    <p v-if="showMessage">{{ dynamicMessage }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'Home',
  setup() {
    // 定义响应式状态
    const showMessage = ref(false);
    const dynamicMessage = ref('按钮点击后显示的动态消息！');

    // 方法：点击按钮时更改 showMessage 状态
    const changeMessage = () => {
      showMessage.value = !showMessage.value;
    };

    return {
      showMessage,
      dynamicMessage,
      changeMessage
    };
  }
});
</script>

<style scoped>
.home {
  text-align: center;
  margin-top: 50px;
}

button {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}

button:hover {
  background-color: #007bff;
  color: white;
}
</style>
