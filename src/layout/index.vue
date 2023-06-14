<template>
  <div class="common-layout">
    <el-container direction="vertical">
        <Header/>
      <el-container class="aside-height">
        <el-aside width="200px">
          <Aside/>
        </el-aside>
        <el-main>
          <Main/>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script setup lang="ts">
import Header from "@/components/Header/index.vue";
import Aside from "@/components/Aside/index.vue"
import Main from "@/components/Main/index.vue"
</script>

<style  lang="less" scoped>
.aside-height{
  height: ~'calc(100vh - 60px)';
}
</style>
