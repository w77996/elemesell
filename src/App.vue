<template>
  <div>
    <v-header></v-header>
    <!-- 主体切换 -->
    <div class="tab border-1px">
      <div class="tab-item">
        <router-link v-bind:to="'/goods'">
          商品
        </router-link>
      </div>
      <div class="tab-item">
        <router-link to="/ratings">
          评论
        </router-link>
      </div>
      <div class="tab-item">
        <router-link to="/seller">
          商家
        </router-link>
      </div>
    </div>
    <!-- 头部 -->
    
  </div>
</template>

<script type="text/ecmascript-6">
import header from './components/header/header.vue';
  export default {
    components: {
      'v-header': header
    }
  };
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .tab
    display: flex
    width: 100%
    height: 40px;
    line-height: 40px;
 
</style>
