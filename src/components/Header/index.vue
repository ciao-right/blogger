<script setup lang="ts">
import {TOptionTitle} from "@/type";

const optionTitle: Array<TOptionTitle> = [
  {
    title: "首页",
    value: "home",
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
</script>

<template>
  <div class="container mx-auto fixed flex">
    <div class="left-header-content flex">
      <div class="logo">
        this is logo
      </div>
      <div class="option-title-content flex">
        <div class="option-title" v-for="(item,index) in optionTitle" :key="index" >
           {{item.title}}
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="less" scoped>
</style>
