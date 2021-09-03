<template>
  <div class="Personal">
    <div class="top">
      <div class="img"></div>
      <div class="name">
        <p>JASON</p>
        <p>Web Engineer</p>
      </div>
      <div class="clear"></div>
      <div class="contact">
        <a href="https://github.com/dream-cheng-927/git-demo"
           class="iconfont icon-github"
           target="_blank"></a>
        <a href="https://www.youtube.com/"
           class="iconfont icon-youtube"
           target="_blank"></a>
        <a class="iconfont icon-twitter"
           title="我关注的全是不可描述，不给你们看"></a>
        <el-popover placement="bottom"
                    :width="150"
                    trigger="click">
          <template #reference>
            <a class="iconfont icon-weixin"></a>
          </template>
          <img style="display: block"
               src="../../assets/img/personal/weixin.png"
               width="150"
               height="150">
        </el-popover>
        <a href="http://wpa.qq.com/msgrd?v=3&uin=2539186615&site=qq&menu=yes"
           class="iconfont icon-QQ"
           target="_blank"></a>
      </div>
    </div>
    <div class="bottom">
      <a href="https://github.com/dream-cheng-927/git-demo"
         target="_blank">DOWNLOAD CV</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "Personal"
}
</script>

<style lang="less" scoped>
.Personal {
  min-width: 270px;
  height: 220px;
  margin-bottom: 35px;
  box-shadow: 0 0 2px #999;
  .top {
    background-color: #bfe2e6;
    .img {
      overflow: hidden;
      float: left;
      width: 60px;
      height: 60px;
      margin-top: 20px;
      margin-left: 30px;
      border: 2px solid #fff;
      border-radius: 50%;
      background: url("../../assets/img/personal/jason.png") no-repeat 50% /
        cover;
    }
    .name {
      float: right;
      margin-top: 29px;
      margin-right: 30px;
      p:nth-child(1) {
        font-size: 25px;
        font-weight: bolder;
        letter-spacing: 5px;
        font-family: "Pacifico";
      }

      p:nth-child(2) {
        font-family: Quicksand;
        color: #555;
        font-weight: 700;
        letter-spacing: 3px;
        font-size: 12px;
        margin-top: 5px;
      }
    }
    .clear {
      width: 0;
      height: 0;
      clear: both;
    }
    .contact {
      margin-top: 15px;
      justify-content: space-around;
      padding-bottom: 20px;
      display: flex;
      a {
        display: block;
        font-size: 25px;
        color: #525252;
        transition: color 0.3s;
        cursor: pointer;
      }
    }
  }
  .bottom {
    width: 100%;
    padding: 20px 0;
    background-color: #fff;
    a {
      display: block;
      width: 65%;
      height: 40px;
      border-radius: 23px;
      margin: 0 auto;
      box-shadow: 0 0 0 #888;
      font-family: Quicksand;
      font-size: 14px;
      text-align: center;
      line-height: 40px;
      font-weight: 700;
      color: #000;
      letter-spacing: 1px;
      background-color: #bfe2e6;
      transition: box-shadow 0.3s;
      &:hover {
        box-shadow: 0 2px 10px #888;
      }
    }
  }
}
</style>