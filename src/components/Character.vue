<script setup>


import {reactive, ref} from "vue";

const active_group = ref('hoshio_stu_union');
const active_chara = ref('hana_ichinose');
const groups = reactive([
  {
    label: '星尾女子高中學生會', name: 'hoshio_stu_union', content: []
  },
  {label: '手鞠住宅樓', name: 'temari_heights', content: []},
  {label: '星尾女子高中1年級生', name: 'hoshio_grade_1', content: []},
  {label: '星尾女子高中2年級生', name: 'hoshio_grade_2', content: []},
  {label: '星尾女子高中3年級生', name: 'hoshio_grade_3', content: []},
  {label: '主要角色家庭成員', name: 'main_chara_families', content: []},
  {label: '其他出場角色', name: 'others', content: [
      {label: '本氣醬?', name: 'maji', content: [
          {entry:'姓名',desc:'本氣(マジちゃん)',source:'《本氣求道》'},
          {desc:'大學生',source:'10卷27p'},
          {desc:'那種有前世姻緣的朋友',source:'@1093yuiko2021.07.10'},
        ]},
      {label: '草千穂?', name: 'kusachiho', content: [
          {entry:'姓名',desc:'草千穂(くさちほ)',source:'《瓶詰妖精》'},
          {desc:'主婦',source:'10卷27p'},
          {desc:'那種有前世姻緣的朋友',source:'@1093yuiko2021.07.10'},
        ]},
      {label: '恵美?', name: 'emi', content: [
          {entry:'姓名',desc:'恵美(えみちゃん)',source:'10卷28p'},
          {entry:'其他',desc:'冠的小初朋友',source:'10卷23p'},
        ]},
      {label: '満?', name: 'mitsuru', content: [
          {entry:'姓名',desc:'満(みつるちゃん)',source:'10卷28p'},
          {entry:'其他',desc:'冠的小初朋友',source:'10卷23p'},
        ]},
      {label: '千鶴?', name: 'chizuru', content: [
          {entry:'姓名',desc:'千鶴(ちづるちゃん)',source:'10卷28p'},
          {entry:'其他',desc:'冠的小初朋友',source:'10卷23p'},
        ]},
    ]},
])
const cols = reactive([
  {name: 'entry', label: '条目', width: '10', align: 'left'},
  {name: 'desc', label: '描述', width: '55', align: 'left'},
  {name: 'source', label: '出处', width: '35', align: 'left'},
])
</script>

<template>
  <el-tabs v-model="active_group" @tab-click="" type="border-card" tabPosition="left">
    <el-tab-pane v-for="group in groups" :label="group.label" :name="group.name">
      <el-tabs v-model="active_chara" @tab-click="" type="border-card" tabPosition="left">
        <el-tab-pane v-for="chara in group.content" :label="chara.label" :name="chara.name">
          <el-table height="71vh" :data="chara.content">
            <el-table-column v-for="col in cols" :header-align="col.align" :align="col.align" :prop=col.name
                             :label=col.label
                             :min-width="col.width">
            </el-table-column>
          </el-table>
        </el-tab-pane>
      </el-tabs>
    </el-tab-pane>
  </el-tabs>
</template>

<style scoped>

</style>