<!-- 组件说明 -->
<template>
  <div class='nav-bar'>
    <div class="left"><slot name="left"></slot></div>
    <div class="center"><slot name="center"></slot></div>
    <div class="right"><slot name="right"></slot></div>
  </div>
</template>

<script>
  //import x from ''
  export default {
    name: "NavBar",
    components: {

    },
    data () {
      return {

      };
    },
    computed: {

    },
    methods: {

    },
  }
</script>

<style scoped>
.nav-bar{
  display: flex;
  line-height: 44px;
  text-align: center;
  box-shadow: 0 1px 1px rgba(100, 100, 100, .1);
}
.left, .right {
  width: 60px;
}
.center {
  flex: 1;
}

</style>