<template>
  <div>
    <!--侧边菜单栏-->
    <leftBar @collapse="handCollapse"></leftBar>
    <!--标签栏-->
    <navbar></navbar>
    <!--主要内容-->
    <div class="transiton" :style="{'margin-left':marginLeft}">
      <tabContent :width="width">
      </tabContent>
    </div>
  </div>
</template>

<script>
import navbar from './navbar';
import leftBar from './leftBar';
import tabContent from './tabContent';
export default {
  name: 'layout',
  components: {
    navbar,
    tabContent,
    leftBar
  },
  data () {
    return {
      width: 'calc(100% - 230px)',
      marginLeft: '200px',
      shadowStatus: false
    };
  },
  methods: {
    handCollapse (isCollapse) {
      if (isCollapse) {
        this.marginLeft = '40px';
        this.width = 'calc(100% - 70px)';
      } else {
        this.marginLeft = '200px';
        this.width = 'calc(100% - 230px)';
      }
    }
  }
};
</script>

<style lang="scss" scoped>
.transiton {
  -webkit-transition: margin 0.2s linear 0.01s;
  transition: margin 0.2s linear 0.01s;
  transition-property: margin;
  transition-duration: 0.2s;
  transition-timing-function: linear;
  transition-delay: 0.01s;
}
</style>
