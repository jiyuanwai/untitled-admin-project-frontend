<template>
  <a-menu theme="light" :defaultSelectedKeys="['1']" mode="inline" style="border:none;">
    <a-menu-item key="1" @click="go('/')">
      <a-icon type="pie-chart" />
      <span>Go to Foo</span>
    </a-menu-item>
    <a-menu-item key="2">
      <a-icon type="desktop" />
      <span>Option 2</span>
    </a-menu-item>
    <a-sub-menu key="sub1">
      <span slot="title">
        <a-icon type="user" />
        <span>User</span>
      </span>
      <a-menu-item key="3" @click="go('/about')">Tom2222222222</a-menu-item>
      <a-menu-item key="4">Bill</a-menu-item>
      <a-menu-item key="5">Alex</a-menu-item>
    </a-sub-menu>
    <a-sub-menu key="sub2">
      <span slot="title">
        <a-icon type="team" />
        <span>Team</span>
      </span>
      <a-menu-item key="6">Team 1</a-menu-item>
      <a-menu-item key="8">Team 2</a-menu-item>
    </a-sub-menu>
    <a-menu-item key="9">
      <a-icon type="file" />
      <span>File</span>
    </a-menu-item>
  </a-menu>
</template>
<script>
export default {
  name: 'ResponsiveMenu',
  methods: {
    go (path) {
      if (this.$route.path !== path) { this.$router.push(path) }
    }
  }
}
</script>
<style scoped>
</style>
