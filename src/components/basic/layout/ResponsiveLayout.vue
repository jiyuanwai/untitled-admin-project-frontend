<template>
  <!-- 显示关闭按钮 style可以固定菜单 breakpoint可以响应式收缩 -->
  <a-layout id="components-layout-demo-responsive">
    <a-layout-sider
      breakpoint="lg"
      theme="light"
      v-model="collapsed"
      collapsible
      @collapse="onCollapse"
      @breakpoint="onBreakpoint"
      class="shadow"
      :style="{ overflow: 'auto', height: '100vh', position: 'fixed', left: 0 }"
    >
      <div class="logo" />
      <ResponsiveMenu />
    </a-layout-sider>
    <a-layout :style="{marginLeft:collapsed?'80px':'200px'}">
      <a-layout-header class="shadow" style="background: #fff; ">
        <!-- <a-icon
          class="trigger"
          :type="collapsed ? 'menu-unfold' : 'menu-fold'"
          @click="()=> collapsed = !collapsed"
        />-->
      </a-layout-header>
      <a-layout-content
        class="shadow"
        :style="{ margin: '24px 16px 0 16px', padding: '16px', background: '#fff'}"
      >
        <router-view></router-view>
      </a-layout-content>
      <a-layout-footer
        :style="{textAlign: 'center', padding: '5px', marginTop: '4px'}"
      >Untiled Admin Project ©2020 Created by Jiyuanwai</a-layout-footer>
    </a-layout>
  </a-layout>
</template>
<script>
import ResponsiveMenu from '../menu/ResponsiveMenu'
export default {
  data () {
    return {
      collapsed: false
    }
  },
  components: { ResponsiveMenu },
  methods: {
    onCollapse (collapsed, type) {
      console.log(collapsed, type)
    },
    onBreakpoint (broken) {
      console.log(broken)
    }
  }
}
</script>

<style lang="less">
.shadow {
  box-shadow: 0 0 4px lightgrey;
}
#components-layout-demo-responsive {
  min-height: 100%;
  .logo {
    height: 32px;
    background: rgba(144, 15, 15, 0.2);
    margin: 16px;
  }
}
</style>
