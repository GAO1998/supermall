<!-- 组件说明 -->
<template>
  <div class="tab-bar-item" @click="itemClick">
    <div v-if="isActive">
      <slot name="item-icon-active"></slot>
    </div>
    <div v-else>
      <slot name="item-icon"></slot>
    </div>

    <div :style="activeStyle">
      <slot name="item-text"></slot>
    </div>
  </div>
</template>

<script>
//import x from ''
export default {
  components: {},
  props:{
    path: String,
    activeColor: {
      type: String,
      default: 'black'
    }
  },
  data() {
    return {
      // isActive: false
    };
  },
  computed: {
    isActive(){
      return this.$route.path.indexOf(this.path) !== -1
    },
    activeStyle(){
      return  this.isActive ? {color: this.activeColor} : {}
    }
  },
  methods: {
    itemClick(){
      this.$router.push(this.path)
    }
  }
};
</script>

<style scoped>
.tab-bar-item {
  flex: 1;
  text-align: center;
  height: 49px;
  font-size: 12px;
  color: gray;
}
.tab-bar-item img {
  width: 28px;
  height: 28px;
  margin-top: 3px;
  vertical-align: middle;
  margin-bottom: 2px;
}

</style>
