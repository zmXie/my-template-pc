<template>
  <div id="app">
    <transition>
      <router-view />
    </transition>
  </div>
</template>
<script>
export default {
  name: 'app',
  components: {
  },
  methods: {
  }
}
</script>
<style lang="scss">
@import "~@/assets/style/index.scss";
</style>
