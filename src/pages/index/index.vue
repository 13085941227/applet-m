<template>
  <div class="container">
    我是首页
    <mptoast></mptoast>
  </div>
</template>

<script>
import mptoast from 'mptoast'

export default {
  components: {
    mptoast
  },
  data() {
    return {
    };
  },
  mounted() {
    this.showToast();
  },
  methods: {
    showToast () {
      this.$mptoast('我是提示信息')
    },
  }
};
</script>

<style scoped>

</style>
