<template>
  <div class="home">
    <HomeHeader></HomeHeader>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :list="iconList"></home-icons>
    <home-recommend :list="recommendList"></home-recommend>
    <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from "./Header";
import HomeSwiper from "./Swiper";
import HomeIcons from "./Icons";
import HomeWeekend from "./Weekend";
import HomeRecommend from "./Recommend";

import axios from "axios";
export default {
  name: "Home",
  data() {
    return {
      msg: "home",
      lastCity: "",
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    };
  },
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeWeekend,
    HomeRecommend
  },
  methods: {
    getHomeInfo() {
      axios
        .get("/api/index.json")
        .then(this.getHomeInfoSucc)
        .catch();
    },
    getHomeInfoSucc(res) {
      res = res.data;
      if (res.ret && res.data) {
        const data = res.data;
        this.swiperList = data.swiperList;
        this.iconList = data.iconList;
        this.recommendList = data.recommendList;
        this.weekendList = data.weekendList;
      }
    }
  },
  mounted() {
    this.lastCity = this.city;
    this.getHomeInfo();
  },
  activated() {
    if (this.lastCity !== this.city) {
      this.lastCity = this.city;
      this.getHomeInfo();
    }
  }
};
</script>

<style scoped>
</style>
