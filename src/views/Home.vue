<template>
  <div class="home">
    <h1>{{count}}</h1>
    <os-button type="primary" size="default" :click="add">点击</os-button>
  </div>
</template>

<script>

export default {
  name: 'Home',
  components: {

  },
  data() {
    return {
      count: 0
    };
  },
  mounted() {

  },
  methods: {
    add() {
      this.count++;
    }
  }
}
</script>
