<script setup>
import Main from './view/Main.vue'
</script>

<template>
  <el-container class="app-container">
    <el-main>
      <Main></Main>
    </el-main>
  </el-container>
</template>

<style scoped>
.app-container {
  height: 100%;
  border: 3px solid var(--el-border-color);
}
</style>
