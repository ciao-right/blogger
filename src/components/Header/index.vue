<script setup lang="ts">
import {ref} from "vue";
import {IHeaderTitle,TNumberOrString} from "@/type";

const optionTitle: Array<IHeaderTitle> = [
  {
    title: "首页",
    value: "layout",
  },
  {
    title: "活动",
    value: "about",
  },
  {
    title: "APP",
    value: "contact",
  },
]

const activeIndex = ref<TNumberOrString>(0)
const avatarUrl: string = 'https://cube.elemecdn.com/3/7c/3ea6beec64369c2642b92c6726f1epng.png'
const handleSelect = (index: number | string) => {
  activeIndex.value = index
}
</script>

<template>
  <div class="container">
    <el-menu
        :default-active="activeIndex"
        mode="horizontal"
        :ellipsis="false"
        @select="handleSelect"
    >
      <el-menu-item index="0">LOGO</el-menu-item>
      <div class="flex-grow"/>
      <el-menu-item index="1">Processing Center</el-menu-item>
      <el-sub-menu index="2">
        <template #title>
          <el-avatar shape="square" :size="30" :src="avatarUrl"/>
        </template>
        <el-menu-item index="2-1">个人中心</el-menu-item>
        <el-menu-item index="2-2">修改密码</el-menu-item>
        <el-menu-item index="2-3">退出登录</el-menu-item>
      </el-sub-menu>
    </el-menu>

  </div>
</template>

<style lang="less" scoped>
.flex-grow {
  flex-grow: 1;
}
</style>
