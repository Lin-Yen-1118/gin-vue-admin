<template>
  <div>
    我是test的父層-上
    <router-view v-slot="{ Component }">
      <transition mode="out-in" name="el-fade-in-linear">
        <keep-alive :include="routerStore.keepAliveRouters">
          <component :is="Component" />
        </keep-alive>
      </transition>
    </router-view>
    我是test的父層-下
  </div>
</template>

<script>
export default {
  name: 'test',
};
</script>
<script setup>
import { useRouterStore } from '@/pinia/modules/router';
const routerStore = useRouterStore();
</script>
