<template>
  <div class="container" @click="showToast">
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
      param: {
        method: 'taobao.item.seller.get',
        app_key: '12345678',
        session: 'test',
        format: 'json',
        timestamp: '2018-04-19 11:47:00',
        v: '2.0',
        sign_method: 'md5',
        fields: 'num_iid,title,nick,price,num',
        num_iid: 11223344
      }
    };
  },
  mounted() {
    this.showToast();
    this.get();
  },
  methods: {
    showToast () {
      this.$mptoast('我是提示信息')
    },
    get: async function () {
      var res =  await this.$request('/router/rest','get',this.param);
      console.log(res);
    }
  }
};
</script>

<style scoped>

</style>
