<!-- 组件说明 -->
<template>
  <div id="home">
    <nav-bar class="home-nav"><div slot="center">购物街</div></nav-bar>
    <home-swiper :banners="banners"></home-swiper>
  </div>
</template>

<script>
import NavBar from "components/common/navbar/NavBar";
import HomeSwiper from './chidrenComps/HomeSwiper'
import { getHomeMultidata } from "network/home";

//import x from ''
export default {
  name: "Home",
  components: {
    NavBar,
    HomeSwiper,
  },
  created(){
    //1. 请求多个数据
    getHomeMultidata().then(res => {
      this.banners = res.data.banner.list;
      this.recommends = res.data.recommend.list;
    })
  },
  data() {
    return {
      banners: [],
      recommends: [],

    };
  },
  computed: {},
  methods: {}
};
</script>

<style scoped>
.home-nav {
  background-color: var(--color-tint);
  color: #fff;
}
</style>
