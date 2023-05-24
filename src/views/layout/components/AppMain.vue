<template>
  <section class="app-main">
    <template v-if="checkMenuAuth">
      <transition name="fade-transform" mode="out-in">
        <keep-alive>
          <router-view :key="key" v-if="isKeepAlive" />
        </keep-alive>
      </transition>
      <transition name="fade-transform" mode="out-in">
        <router-view :key="key" v-if="!isKeepAlive" />
      </transition>
    </template>
    <template v-else>
      <page-no-permission></page-no-permission>
    </template>
  </section>
</template>

<script>
import pageNoPermission from '@/views/system/error/page-no-permission.vue'
export default {
  name: 'AppMain',
  components: { pageNoPermission },
  computed: {
    key() {
      return this.$route.fullPath
    },
    isKeepAlive() {
      return this.$route.meta?.isKeepAlive;
    },
    /*校验权限*/
    checkMenuAuth() {
      return true;
    },
  }
}
</script>

<style scoped>
.app-main {
  height: calc(100vh - 50px);
  width: 100%;
  position: relative;
  overflow: hidden;
}
.fixed-header + .app-main {
  padding-top: 50px;
  height: 100vh;
}
.app-main > div {
  height: 100%;
  padding: 20px;
  overflow: auto;
}
</style>

<style lang="scss">
.el-popup-parent--hidden {
  .fixed-header {
    padding-right: 15px;
  }
}
</style>
