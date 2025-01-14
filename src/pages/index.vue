<!--
 * @Author: weisheng
 * @Date: 2024-11-01 11:44:38
 * @LastEditTime: 2024-11-01 14:10:20
 * @LastEditors: weisheng
 * @Description:
 * @FilePath: \wot-demo\src\pages\index.vue
 * 记得注释
-->
<script setup lang="ts">
import Comp from './Comp.vue'

const tab = ref(0)
const tabs = [
  { title: '公告' },
  { title: '人事人才头条' },
  { title: '学习指南' },
  { title: '政策资讯' },
]
</script>

<template>
  <view>
    <wd-tabs v-model="tab" animated swipeable slidable="always">
      <block v-for="(item, index) in tabs" :key="item.title">
        <wd-tab :title="item.title">
          <view v-if="tab === index">
            <Comp>
              <template #default="{ data }">
                <view>{{ data }}</view>
              </template>
            </Comp>
          </view>
        </wd-tab>
      </block>
    </wd-tabs>
  </view>
</template>

<style></style>

<route type="home" lang="json">
{
  "layout": "tabbar",
  "name": "home",
  "style": {
    "navigationBarTitleText": "home"
  }
}
</route>
