<template>
  <div id="home">
    <nav-bar id="home-nav">
      <div slot="center">购物街</div>
    </nav-bar>
    <home-swiper :banner="banner"></home-swiper>
    <recommend-view :recommend="recommend"></recommend-view>
  </div>
</template>

<script>
import NavBar from "@/components/common/navbar/NavBar";
import HomeSwiper from "@/views/home/childComp/HomeSwiper";
import RecommendView from "@/views/home/childComp/RecommendView";

import { getHomeMultidata } from "network/home.js";
export default {
  name: "Home",
  components: {
    NavBar,
    HomeSwiper,
    RecommendView
  },
  data() {
    return {
      banner: [],
      recommend: []
    };
  },
  created() {
    getHomeMultidata().then(res => {
      console.log(res.data);
      this.banner = res.data.banner.list;
      this.recommend = res.data.recommend.list;
    });
  }
};
</script>

<style>
#home-nav {
  background-color: var(--color-tint);
  color: white;
}
</style>