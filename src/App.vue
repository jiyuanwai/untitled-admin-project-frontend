<template>
  <a-locale-provider :locale="zh_CN">
    <div id="app">
      <ResponsiveLayout />
    </div>
  </a-locale-provider>
</template>

<script>
import zh_CN from 'ant-design-vue/lib/locale-provider/zh_CN'
import ResponsiveLayout from './components/basic/layout/ResponsiveLayout'

export default {
  name: 'app',
  data () {
    return {
      zh_CN
    }
  },
  components: {
    ResponsiveLayout
  }
}
</script>

<style>
#app {
  height: 100%;
}
</style>
