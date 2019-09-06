<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont">&#xe646;</span>
    </div>
    <div class="header-input">内容</div>
    <router-link to="/city">
      <div class="header-right" @click="gotoCity">
        <span>北京</span>
        <span class="iconfont">&#xe64a;</span>
      </div>  
  </div>
</template>

<script>
export default {
  name: "HomeHeader",
  data() {
    return {
      msg: "home"
    };
  }
};
</script>

<style lang="stylus" scoped>
.header {
  line-height: 0.86rem;
  display: flex;
  height: 0.86rem;
  background: #00bcd4;
  color: #fff;

  .header-left {
    width: 0.68rem;
    float: left;
    text-align: center;
  }

  .header-input {
    padding-left: 0.1rem;
    flex: 1;
    margin-top: 0.12rem;
    margin-bottom: 0.12rem;
    margin-left: 0.12rem;
    margin-right: 0.12rem;
    background: #fff;
    border-radius: 0.1rem;
    color: #ccc;
    height: 0.64rem;
    line-height: 0.64rem;
  }

  .header-right {
    width: 1.24rem;
    text-align: center;
    color: #fff;
  }
}
</style>
