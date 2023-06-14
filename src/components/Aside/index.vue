<script setup lang="ts">
import {ref,onMounted} from "vue";
import {TNumberOrString} from "@/type";
import {Menu as IconMenu, Location, Setting, Document} from "@element-plus/icons-vue";
const handleOpen = (key: string, keyPath: string[]) => {
}
const handleClose = (key: string, keyPath: string[]) => {
}

const getDefaultActiveMenu = (id: string): string => {
  return ""
}
const defaultActive = ref<TNumberOrString>("")
const activeMenu = ref<TNumberOrString>(defaultActive.value)
onMounted(() => {
  //todo 通过路由还是用户id获取默认选中的菜单
  defaultActive.value = getDefaultActiveMenu("1")
})
</script>

<template>
  <div class="container">
    <el-menu
        :default-active="activeMenu"
        @open="handleOpen"
        @close="handleClose"
        style="height: 100%;"
    >
      <el-sub-menu index="1">
        <template #title>
          <el-icon>
            <Location/>
          </el-icon>
          <span>Navigator One</span>
        </template>
        <el-menu-item-group title="Group One">
          <el-menu-item index="1-1">item one</el-menu-item>
          <el-menu-item index="1-2">item two</el-menu-item>
        </el-menu-item-group>
        <el-menu-item-group title="Group Two">
          <el-menu-item index="1-3">item three</el-menu-item>
        </el-menu-item-group>
        <el-sub-menu index="1-4">
          <template #title>item four</template>
          <el-menu-item index="1-4-1">item one</el-menu-item>
        </el-sub-menu>
      </el-sub-menu>
      <el-menu-item index="2">
        <el-icon>
          <IconMenu/>
        </el-icon>
        <span>Navigator Two</span>
      </el-menu-item>
      <el-menu-item index="3" disabled>
        <el-icon>
          <Document/>
        </el-icon>
        <span>Navigator Three</span>
      </el-menu-item>
      <el-menu-item index="4">
        <el-icon>
          <Setting/>
        </el-icon>
        <span>Navigator Four</span>
      </el-menu-item>
    </el-menu>
  </div>
</template>

<style lang="less" scoped>

</style>
