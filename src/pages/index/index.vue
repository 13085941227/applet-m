/*
 * @Author: wangjiawei 
 * @Date: 2018-04-20 10:03:42 
 * @Last Modified by: wangjiawei
 * @Last Modified time: 2018-04-20 10:09:34
 */

<template>
  <div class="container" @click="showToast">
    我是首页
    <mptoast></mptoast>
  </div>
</template>

<script>
import mptoast from "mptoast";
export default {
  components: {
    mptoast
  },
  data() {
    return {
      param: {
        method: "taobao.item.seller.get",
        app_key: "12345678",
        session: "test",
        format: "json",
        timestamp: "2018-04-19 11:47:00",
        v: "2.0",
        sign_method: "md5",
        fields: "num_iid,title,nick,price,num",
        num_iid: 11223344
      }
    };
  },
  mounted() {
    this.showToast();
    this.$request("/router/rest", "get", this.param).then((res)=>{
      console.log(res);
    });
  },
  methods: {
    showToast() {
      this.$mptoast("我是提示信息");
    },
  }
};
</script>

<style scoped>

</style>
