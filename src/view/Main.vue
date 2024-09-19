<script setup>
import {ref} from "vue";
import Call from '../components/Call.vue'
import Character from "../components/Character.vue";
import Terminology from "../components/Terminology.vue";
import Timeline from '../components/Timeline.vue'
import School from "../components/School.vue";


const active_tab = ref('timeline')

</script>

<template>
  <el-tabs v-model="active_tab" @tab-click="" type="border-card">
    <el-tab-pane label="角色" name="character">
      <Character></Character>
    </el-tab-pane>
    <el-tab-pane label="称呼" name="call">
      <Call></Call>
    </el-tab-pane>
    <el-tab-pane label="用语" name="terminology">
      <Terminology></Terminology>
    </el-tab-pane>
    <el-tab-pane label="學校" name="school">
      <School></School>
    </el-tab-pane>
    <el-tab-pane label="时间线" name="timeline">
      <Timeline></Timeline>
    </el-tab-pane>
  </el-tabs>
</template>

<style scoped>

</style>