<template>
  <AppNav></AppNav>
  <div id="main">
    <div class="left">
      <AppSide></AppSide>
    </div>
    <div class="right">
      <router-view />
    </div>
  </div>
</template>

<script>
import AppNav from "./components/AppNav";
import AppSide from "./components/AppSide";
import { mapMutations } from "vuex"
export default {
  components: {
    AppNav, AppSide
  },
  methods: {
    ...mapMutations(['loginSuccess'])
  },
  async created () {
    let { data } = await this.$axios({
      method: "POST",
      url: "/login/check"
    })
    //未登录
    if (data.code) return
    //已登录
    this.loginSuccess(data.data)
  }
}
</script>

<style lang="less">
@import "assets/css/reset.css";
@import "assets/css/font.css";
@import "assets/css/font/iconfont.css";
::-webkit-scrollbar {
  /*滚动条整体样式*/
  width: 5px; /*高宽分别对应横竖滚动条的尺寸*/
  height: 5px;
}
::-webkit-scrollbar-thumb {
  /*滚动条里面小方块*/
  border-radius: 5px;
  -webkit-box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.2);
  background: rgba(0, 167, 232, 0.3);
}
::-webkit-scrollbar-track {
  /*滚动条里面轨道*/
  -webkit-box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.2);
  border-radius: 10px;
  background: #ededed;
}

body {
  margin-top: 60px;
  background-color: #f2f2f2;
  background: url("assets/img/bg/bg-left.png") no-repeat 0 50px fixed,
    url("assets/img/bg/bg-right.png") no-repeat right 50px fixed;
}
#main {
  box-sizing: border-box;
  max-width: 1450px;
  display: flex;
  width: 100%;
  padding: 0 15px;
  margin: 15px auto 0;
  > .left {
    width: 270px;
    height: 500px;
    margin-right: 15px;
  }
  > .right {
    flex: 1;
    height: 500px;
  }
}
</style>
