<template>
  <div class="pub-header">
    <span v-if="back=='true'" class="extend-click header-icon header-left" @click="goBack()"></span>
    <div class="header-content">
      {{headerTitle}}




      <slot></slot>
    </div>
  </div>
</template>
<script>
export default {
  props: ['headerTitle', 'back'],
  methods: {
    goBack () {
      // 坑
      this.$router.go(-1)
    }
  }
}
</script>
<style lang="less" scoped>
.pub-header{
  height: 4.5rem;
  line-height: 4.5rem;
  background-color: #f9fafd;
  position: fixed;
  width: 100%;
  text-align: center;
  z-index: 2;
  font-size: 1.4rem;
  font-weight: 700;
}
.header-content{
  position: absolute;
  left: 6rem;
  right: 6rem;
}
.header-icon{
  position: absolute;
  top: 0;
  width: 6rem;
  height: 4.4rem;
  background-repeat: no-repeat;
  -webkit-background-size: auto 2.5rem;
  background-size: auto 2.5rem;
  background-position: left center;
}
.header-left{
  background-image: url("./images/header-icon.png");
  left: .6rem;
}
</style>
